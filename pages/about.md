---
layout: page
title: About
description: Hello Word
keywords: WINDOWS USER
comments: true
menu: 关于
permalink: /about/
---

我是马壮，码而生，码而立。

仰慕「优雅编码的艺术」。

坚信熟能生巧，努力改变人生。

## 联系

<ul>
{% for website in site.data.social %}
<li>{{website.sitename }}：<a href="{{ website.url }}" target="_blank">@{{ website.name }}</a></li>
{% endfor %}
{% if site.url contains 'mazhuang.org' %}
<li>
Bu是公众号：<br />
<img style="height:192px;width:192px;border:1px solid lightgrey;" src="{{ site.url }}/assets/images/zhanyong.jpg" alt="什么也没有" />
</li>
{% endif %}
</ul>



## Skill Keywords

{% for skill in site.data.skills %}
### {{ skill.name }}
<div class="btn-inline">
{% for keyword in skill.keywords %}
<button class="btn btn-outline" type="button">{{ keyword }}</button>
{% endfor %}
</div>
{% endfor %}
