# Frequently Asked Questions

<br/><br/>

<span class='row' markdown="1">


<div class="panel-group" id="accordion" role="tablist" aria-multiselectable="true" markdown="1">

{% for question in site.data.faq %}

{% assign qid_head = "heading" | append: question.filename | remove: '.md' %} 
{% assign qid_div = "collapse" | append: question.filename | | remove: '.md' %}



<div class="panel panel-default" markdown="1">

<div class="panel-heading" role="tab" id="{{ qid_head }}" markdown="1">
<h4 class="panel-title text-left" markdown="1">
<a class="collapsed" role="button" data-toggle="collapse" data-parent="#accordion" href="#{{ qid_div }}" aria-expanded="false" aria-controls="{{ qid_div }}">
  {{ question.question }}
</a>
</h4>
</div>

<div id="{{ qid_div }}" class="panel-collapse collapse" role="tabpanel" aria-labelledby="{{ qid_head }}">
<div class="panel-body text-left" markdown="1">

### Answer:

{% include {{ question.filename }} %}

</div>
</div>

</div>


{% endfor %}


</div>




<script>

$('#accordion').on('shown.bs.collapse', function (e) {

  // Validate this panel belongs to this accordian, and not an embedded one
  //var actualAccordianId = $('a[href="#' + $(e.target).attr('id') + '"').data('parent');
  var actualAccordianId = $('a[href="#' + $(e.target).attr('id') + '"]').data('parent');
  var targetAccordianId = '#' + $(this).attr('id');
  if (actualAccordianId !== targetAccordianId) return;

  var clickedHeader = $(this).find('.panel > .collapse.in').closest('.panel').find('.panel-heading');
  var offset = clickedHeader.offset();
  var top = $(window).scrollTop();
  if(offset) {
    var topOfHeader = offset.top;
    if(topOfHeader < top) {
      $('html,body').animate({ scrollTop: topOfHeader}, 1000, 'swing');
    }
  }
});

</script>