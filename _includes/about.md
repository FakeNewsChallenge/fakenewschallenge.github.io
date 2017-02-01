

# About

<span class='row' markdown="1">
<div class='col-md-1'></div>
<div class='text-left' markdown="1">
Fake News Challenge is a grassroots effort of over 100 volunteers and 71 teams from academia and industry around the world. Our goals is to address the problem of fake news by organizing a competition to foster development of  tools to help human fact checkers identify hoaxes and deliberate misinformation in news stories using machine learning, natural language processing and artificial intelligence.
</div>
{: .col-md-10 .whitepane .pane .row}

<span class='row' markdown="1">

<br>
<br/>

## Advisors
{: .col-md-12 .whitepane .pane}
<br/>


{% for member in site.data.advisors %}

{% if member.photo == "" or member.photo == nil %}
 {% assign photo = "nopic.gif" %}
{% else %}
 {% assign photo = member.photo %}
{% endif %}

{% if member.title == "" or member.title == nil %}
 {% assign title = "TBD" %}
{% else %}
 {% assign title = member.title %}
{% endif %}

{% if member.affiliation == "" or member.affiliation == nil %}
 {% assign affiliation = "TBD" %}
{% else %}
 {% assign affiliation = member.affiliation %}
{% endif %}

{% if member.homepage == "" or member.homepage == nil %}
 {% assign homepage = "#" %}
{% else %}
 {% assign firstfour = member.homepage | slice: 0, 4 %}
 {% if firstfour == "http" %}
  {% assign homepage = member.homepage %}
 {% else %}
  {% assign homepage = "http://" | append: member.homepage %}
 {% endif %}
{% endif %}


{% if member.twitter == "" or member.twitter == nil %}
 {% assign twitter = "#" %}
{% else %}
 {% assign twitter = "https://twitter.com/" | append: member.twitter %}
{% endif %}


> ![{{ member.name photo }}]({{ site.baseurl}}/assets/img/{{ photo }}){: height="192px" width="192px"}
>
> #### {{ member.name }}
> *{{ title }}*{:.team-title} <br/>
> *{{ affiliation }}*{:.team-title} <br/>
>
> - <a href="{{ homepage }}"><i class="fa fa-home"></i>
> - <a href="{{ twitter }}"><i class="fa fa-twitter"></i>
> {: .list-inline .social-buttons}
{: .team-member .col-sm-4 .noleftborder}

{% endfor %}    

<span class='row' markdown="1">

## Organizers 
{: .col-md-12 .whitepane .center-align .pane}
<br/>

{% for member in site.data.organizers %}

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

{% if member.homepage == "" or member.homepage == nil %}
 {% assign homepage = "#" %}
{% else %}
 {% assign firstfour = member.homepage | slice: 0, 4 %}
 {% if firstfour == "http" %}
  {% assign homepage = member.homepage %}
 {% else %}
  {% assign homepage = "http://" | append: member.homepage %}
 {% endif %}
{% endif %}


{% if member.twitter == "" or member.twitter == nil %}
 {% assign twitter = "#" %}
{% else %}
 {% assign twitter = "https://twitter.com/" | append: member.twitter %}
{% endif %}


> ![{{ member.name photo }}]({{ site.baseurl}}/assets/img/{{ photo }}){: height="192px" width="192px"}
>
> #### {{ member.name }}
> *{{ affiliation }}*{:.team-title} <br/>
> *{{ title }}*{:.team-title}
>
> - <a href="{{ homepage }}"><i class="fa fa-home"></i>
> - <a href="{{ twitter }}"><i class="fa fa-twitter"></i>
> {: .list-inline .social-buttons}
{: .team-member .col-sm-4 .noleftborder}

{% endfor %}





<span class='row' markdown="1">

## Key Volunteers
{: .col-md-12 .whitepane .center-align .pane}
<br/>

{% for member in site.data.keyvolunteers %}

{% if member.photo == "" or member.photo == nil %}
 {% assign photo = "nopic.gif" %}
{% else %}
 {% assign photo = member.photo %}
{% endif %}

{% if member.title == "" or member.title == nil %}
 {% assign title = "TBD" %}
{% else %}
 {% assign title = member.title %}
{% endif %}

{% if member.homepage == "" or member.homepage == nil %}
 {% assign homepage = "#" %}
{% else %}
 {% assign firstfour = member.homepage | slice: 0, 4 %}
 {% if firstfour == "http" %}
  {% assign homepage = member.homepage %}
 {% else %}
  {% assign homepage = "http://" | append: member.homepage %}
 {% endif %}
{% endif %}


{% if member.twitter == "" or member.twitter == nil %}
 {% assign twitter = "#" %}
{% else %}
 {% assign twitter = "https://twitter.com/" | append: member.twitter %}
{% endif %}


> ![{{ member.name photo }}]({{ site.baseurl}}/assets/img/{{ photo }}){: height="192px" width="192px"}
>
> #### {{ member.name }}
> <br>
>
> - <a href="{{ homepage }}"><i class="fa fa-home"></i>
> - <a href="{{ twitter }}"><i class="fa fa-twitter"></i>
> {: .list-inline .social-buttons}
{: .team-member .col-sm-4 .noleftborder}

{% endfor %}
