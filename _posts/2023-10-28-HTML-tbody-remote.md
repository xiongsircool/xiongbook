---
layout: post
title: 关于HTML tbody，theed，tfoot使用说明
categories: HTML table tbody，theed，tfoot使用说明
description: 回忆一下 tbody，theed，tfoot 在table中干了什么.
keywords: HTML,table
---

## 关于HTML tbody，theed，tfoot使用说明

太久没有使用HTML写网页了，都忘记得差不多了，但是今天写一个项目用到了利用python 将我的数据转化为PDF方便非代码人员在爬取的数据上进行做笔记什么的。其中思路就是HTMML-转 PDF 。

其中涉及到了我想要将有些数据以表格方式展示，一部分数据以段诺方式展示。然后想起之前写表格代码时候我经常会用到`<table> `里面加 `<tbody>`所以回忆一下，其中这三个命令都是行位置调整命令.

`<table>`元素在HTML中用于表示表格数据，而`<thead>`, `<tbody>`, 和`<tfoot>`是用于对表格内容进行分组的元素。以下是这些元素的用途说明：

1. **`<thead>` (Table Head)**
    - 用于分组表格的头部内容。
    - 通常包含一行或多行的表头(`<th>`)元素，这些元素定义了表格的列标题。
    - 浏览器通常会为`<thead>`中的内容提供特殊的格式，例如加粗字体，以区分其他表格内容。
    - 如果表格很长并跨越多个页面，一些打印机和屏幕阅读器可能会在每一页上重复`<thead>`的内容。

2. **`<tbody>` (Table Body)**
    - 用于分组表格的主体内容。
    - 包含表格的主要数据行。
    - 一个表格可以有多个`<tbody>`元素，这允许您将表格数据分组。例如，您可以为每个月的数据使用一个单独的`<tbody>`。

3. **`<tfoot>` (Table Foot)**
    - 用于分组表格的底部内容。
    - 通常包含一行或多行的单元格(`<td>`或`<th>`)，这些单元格提供了关于表格数据的总结或脚注。
    - 尽管`<tfoot>`在源代码中可能位于`<tbody>`之前，但浏览器会确保它在页面上渲染时始终位于表格的底部。
    - 与`<thead>`类似，如果表格很长并跨越多个页面，一些打印机和屏幕阅读器可能会在每一页上重复`<tfoot>`的内容。

也就是说，这三个可以帮助我们表格进行定位，同时基于查找的信息，使用tbody可以进一步优化表格，以及可以提高同一表格中行显示的优先级。

下面我打乱了表格显示的顺序先写的`<tfoot>`,

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Shuffled Table Example</title>
    <style>
        table {
            width: 100%;
            border-collapse: collapse;
        }
        th, td {
            border: 1px solid black;
            padding: 8px 12px;
            text-align: left;
        }
        th {
            background-color: #f2f2f2;
        }
    </style>
</head>
<body>

<table>
    <!--表格的最后一行我写在了表格的顶部-->
    <tfoot>
        <tr>
            <td colspan="3">Table Footer: Summary or Notes</td>
        </tr>
    </tfoot>
    <tbody>
        <tr>
            <td>Data line 1</td>
            <td>Data line 1</td>
            <td>Data line 1</td>
        </tr>
        <tr>
            <td>Data line 2</td>
            <td>Data line 2</td>
            <td>Data line 2</td>
        </tr>
         <tr>
            <td>Data line 3</td>
            <td>Data line 3</td>
            <td>Data line 3</td>
        </tr>
        
    </tbody>
    <!--标题我写在了表格的底部-->
    <thead>
        <tr>
            <th>Header 1</th>
            <th>Header 2</th>
            <th>Header 3</th>
        </tr>
    </thead>
</table>

</body>
</html>
```



显示效果如下

<table>
    <tfoot>
        <tr>
            <td colspan="3">Table Footer: Summary or Notes</td>
        </tr>
    </tfoot>
    <tbody>
        <tr>
            <td>Data line 1</td>
            <td>Data line 1</td>
            <td>Data line 1</td>
        </tr>
        <tr>
            <td>Data line 2</td>
            <td>Data line 2</td>
            <td>Data line 2</td>
        </tr>
         <tr>
            <td>Data line 3</td>
            <td>Data line 3</td>
            <td>Data line 3</td>
        </tr>
    </tbody>
    <thead>
        <tr>
            <th>Header 1</th>
            <th>Header 2</th>
            <th>Header 3</th>
        </tr>
    </thead>
</table>