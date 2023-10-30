---
layout: post
title: 不得不说这个PDF可视化方案我可太喜欢的了
categories: python
description: 这是一个利用Python 定制化输出PDF的方案
keywords: PDF, python, pdfkit
---


## 不得不说这个PDF可视化方案我可太喜欢的了

There seems to be a lot of steps in your code. You could simply loop over the columns of your transposed df and export each of them to html. Append all html tables to a root html element and export with `pdfkit`:

```py
import json
import pandas as pd
import lxml.etree as et
import pdfkit

your_json = """{"url": "https://www.abc123.com", "extensionVersion": "4.51.0", "axeVersion": "4.6.3", "standard": "WCAG 2.1 AA", "testingStartDate": "2023-04-03T09:35:06.177Z", "testingEndDate": "2023-04-03T09:35:06.177Z", "bestPracticesEnabled": false, "issueSummary": {"critical": 2, "moderate": 0, "minor": 0, "serious": 0, "bestPractices": 0, "needsReview": 0}, "remainingTestingSummary": {"run": false}, "igtSummary": [], "failedRules": [{"name": "button-name", "count": 1, "mode": "automated"}, {"name": "select-name", "count": 1, "mode": "automated"}], "needsReview": [], "allIssues": [{"ruleId": "button-name", "description": "Ensures buttons have discernible text", "help": "Buttons must have discernible text", "helpUrl": "https://www.abc123.com", "impact": "critical", "needsReview": false, "isManual": false, "selector": [".livechat-button"], "summary": "Fix any of the following:\\n  Element does not have inner text that is visible to screen readers\\n  aria-label attribute does not exist or is empty\\n  aria-labelledby attribute does not exist, references elements that do not exist or references elements that are empty\\n  Element has no title attribute\\n  Element's default semantics were not overridden with role=\\"none\\" or role=\\"presentation\\"", "source": "<button class=\\"livechat-button items-center bg-black shadow-liveChat rounded-full text-white p-2 h-12 transition-all opacity-0 pointer-events-none w-sp-48 opacity-0 pointer-events-none\\">", "tags": ["cat.name-role-value", "wcag2a", "wcag412", "section508", "section508.22.a", "ACT"], "igt": "", "shareURL": "", "createdAt": "2023-04-03T09:35:06.177Z", "testUrl": "", "testPageTitle": "ABC123", "foundBy": "ab@bc.com", "axeVersion": "4.6.3"}, {"ruleId": "select-name", "description": "Ensures select element has an accessible name", "help": "Select element must have an accessible name", "helpUrl": "https://www.abc123.com", "impact": "critical", "needsReview": false, "isManual": false, "selector": ["#plp__sortSelected"], "summary": "Fix any of the following:\\n  Form element does not have an implicit (wrapped) <label>\\n  Form element does not have an explicit <label>\\n  aria-label attribute does not exist or is empty\\n  aria-labelledby attribute does not exist, references elements that do not exist or references elements that are empty\\n  Element has no title attribute\\n  Element's default semantics were not overridden with role=\\"none\\" or role=\\"presentation\\"", "source": "<select class=\\"w-full absolute opacity-0 appearance-none text-value-small font-bold text-black uppercase cursor-pointer bg-transparent outline-0\\" id=\\"plp__sortSelected\\">", "tags": ["cat.forms", "wcag2a", "wcag412", "section508", "section508.22.n", "ACT"], "igt": "", "shareURL": "", "createdAt": "2023-04-03T09:35:06.177Z", "testUrl": "https://www.abc123.com", "testPageTitle": "ABC123", "foundBy": "ab@bc.com", "axeVersion": "4.6.3"}]}"""
data = json.loads(your_json)

## replace the above lines with the following in your case
# with open('your_file.json', 'r') as f:   
#     data = json.load(f)

html = et.Element("html")

# general info
html.append(et.fromstring(f"""<h3>Site link: <a href="{data['url']}">{data['url']}</a></h3>"""))
html.append(et.fromstring(f"""<h4>Date: {data['testingEndDate']}</h4>"""))
html.append(et.fromstring(f"""<h4>Summary:</h4>"""))

# summary table
summary = pd.Series(data['issueSummary'])
summary_table = et.fromstring(summary.to_frame().to_html(header=False))
summary_table.set('class', 'summary')
html.append(summary_table)

# issue tables
cols_of_interest = ['ruleId', 'description', 'help', 'impact', 'selector', 'summary', 'source']
df = pd.DataFrame(data['allIssues'])[cols_of_interest].T
for col in df.columns:
    table = et.fromstring(df[[col]].to_html(header=False))
    table.set('class', 'issue')
    html.append(table)
    html.append(et.fromstring('<br/>'))

pdfkit.from_string(et.tostring(html, encoding="unicode"), "./output.pdf", css='style.css')
```

With the following css file:

```css
/* style.css */
* {
    font-family: 'Liberation Sans';
}

table {
    margin: 20px;
    margin-left: auto;
    margin-right: auto;
}

table.summary {
    width: 50%;
}

table.issue{
    border: 0;
    width: 100%;
    border-collapse: collapse;
  }
  
table.issue td,
table.issue th {
    border: 0;
    text-align: left;
    padding: 5px;
}

table.issue tr {
border-bottom: 1px solid #dddddd;
}
```

You'll get:

[![enter image description here](https://i.stack.imgur.com/5qdBq.png)](https://i.stack.imgur.com/5qdBq.png)

Edit: updated json with the data you provided + exporting additional data + improved css

Note: you will need to install [wkhtmltopdf](https://wkhtmltopdf.org/downloads.html) and make sure that it is in your path.