# Timeline

<br/><br/>

<span class="row col-lg-12">

{% for event in site.data.timeline %}
{% if event.status == "finished" %}
{% assign classes="timeline-panel timeline-finished" %}
{% elsif event.status == "last" %}
{% assign classes="timeline-panel no-downarrow" %}
{% else %}
{% assign classes="timeline-panel" %}
{% endif %}
{% if event.inverted == true %}
* {:.timeline-inverted} <div class="{{ classes }}" markdown="1">
#### {{ event.title }} 
{{ event.date }}
{% else %}
* <div class="{{ classes }}" markdown="1">
#### {{ event.title }} 
{{ event.date }}
{% endif %}
{% endfor %}
{: .timeline}