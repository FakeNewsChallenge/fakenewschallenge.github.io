# Frequently Asked Questions

<br/><br/>

{% for question in site.data.faq %}

<span class='row' markdown="1">
<div class='col-md-2'></div>
- 
#### {{ question.question }}
    - {{ question.answer }}
{: .text-left .pane .col-md-8}

{% endfor %}