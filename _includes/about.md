

# About

<span class='row' markdown="1">

<hr class="page_divider col-md-12 row">

<span class='row' markdown="1">


<span class='row' markdown="1">
<div class='col-md-1'></div>

#### <FNC Blurb>
{: .col-md-10 .whitepane .pane .row}

<span class='row' markdown="1">


<br/>

<hr class="page_divider col-md-12 row">

<br/>
<br/>

## Advisors
{: .col-md-12 .whitepane .pane}
<br/>

{% assign memberIndex = 0 %}

{% for member in site.data.advisors %}

{% if member.photo == "" or member.photo == nil %}
{% assign photo = "nopic.gif" %}
{% else %}
{% assign photo = member.photo %}
{% endif %}

{% if member.affiliation == "" or member.affiliation == nil %}
:{% assign affiliation = "TBD" %}
{% else %}
{% assign affiliation = member.affiliation %}
{% endif %}

> ![{{ member.name photo }}]({{ site.baseurl}}/assets/img/{{ photo }}){: height="192px" width="192px"}
>
> #### {{ member.name }}
> *{{ affiliation }}*{:.team-title} <br/>
>
> - <a href="http://{{ member.homepage }}"><i class="fa fa-home"></i>
> - <a href="https://twitter.com/{{ member.twitter }}"><i class="fa fa-twitter"></i>
> {: .list-inline .social-buttons}
{: .team-member .col-sm-4 .noleftborder}

{% assign memberIndex = memberIndex | plus: 1 %}


{% endfor %}    


## Volunteers
{: .col-md-12 .whitepane .pane}
<br/>

{% assign memberIndex = 0 %}

{% for member in site.data.people %}

{% if member.photo == "" or member.photo == nil %}
{% assign photo = "nopic.gif" %}
{% else %}
{% assign photo = member.photo %}
{% endif %}

{% if member.affiliation == "" or member.affiliation == nil %}
{% assign affiliation = "TBD" %}
{% else %}
{% assign affiliation = member.affiliation %}
{% endif %}

{% if member.title == "" or member.title == nil %}
{% assign title = "TBD" %}
{% else %}
{% assign title = member.title %}
{% endif %}


> ![{{ member.name photo }}]({{ site.baseurl}}/assets/img/{{ photo }}){: height="192px" width="192px"}
>
> #### {{ member.name }}
> *{{ affiliation }}*{:.team-title} <br/>
> *{{ title }}*{:.team-title}
>
> - <a href="http://{{ member.homepage }}"><i class="fa fa-home"></i>
> - <a href="https://twitter.com/{{ member.twitter }}"><i class="fa fa-twitter"></i>
> - <a href="https://github.com/{{ member.github }}"><i class="fa fa-github"></i>
> - <a href="#"><i class="fa fa-linkedin"></i>
> {: .list-inline .social-buttons}
{: .team-member .col-sm-4 .noleftborder}

{% assign memberIndex = memberIndex | plus: 1 %}


{% endfor %}