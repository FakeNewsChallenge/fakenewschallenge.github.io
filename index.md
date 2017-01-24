---
layout: agency
---

{% include nav.html cpages=site.data.content %}

<header>
<div class="container">
<div class="intro-text">
<div class='wordcloud intro-heading'></div>
<div class="intro-lead-in">Exploring how artificial intelligence technologies could
be leveraged to combat fake news.</div>
    <div class='row'>
        <div class='col-sm-4 button-spacer'>
            <a href="https://docs.google.com/forms/d/e/1FAIpQLSfJAMXy_iOXnfh-m6jbsbRAm0xwFUlQRD5VWLyuExq2rD0GmQ/viewform" class="page-scroll btn btn-xl">Register A Team</a>
        </div>
        <div class='col-sm-4 button-spacer'>
            <a href="https://github.com/FakeNewsChallenge" class="page-scroll btn btn-xl">Our Github repositories</a>
        </div>
        <div class='col-sm-4 button-spacer'>
            <a  href="https://fakenewschallenge-inviter.herokuapp.com/" class="page-scroll btn btn-xl">Join the Slack</a>
        </div>
    </div><br/><br/>
    <div class='row'>
        <div class='col-sm-4'></div>
            <div class='col-sm-4 button-spacer'>
                <a  href="#stageone" class="page-scroll btn btn-xl"><i class="fa fa-hand-o-down" aria-hidden="true"></i></a>
            </div>
    </div>
</div>
</div>
</header>


{% for page in site.data.content %}

<section id="{{ page.id }}" class="container content-section text-center" markdown="1">
<div class="container" markdown="1">

{% include {{ page.filename }} %}

</div>
</section>

<hr class='page_divider'>

{% endfor %}
