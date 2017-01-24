# Timeline

<br/><br/>

<span class="row col-lg-12">

{% for event in site.data.timeline %}
{% if event.inverted == true %}
* {:.timeline-inverted} <div class="timeline-panel" markdown="1">
#### {{ event.title }} 
{{ event.date }}
{% else %}
* <div class="timeline-panel" markdown="1">
#### {{ event.title }} 
{{ event.date }}
{% endif %}
{% endfor %}
{: .timeline}

