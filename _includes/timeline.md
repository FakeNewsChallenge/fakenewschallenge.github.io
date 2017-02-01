# Timeline

{::options parse_block_html="true" /}

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
* {:.timeline-inverted}{% include timeline_bubble.html event=event classes=classes %}
{% else %}
* {% include timeline_bubble.html event=event classes=classes %}
{% endif %}

{% endfor %}
{: .timeline}

{::options parse_block_html="false" /}