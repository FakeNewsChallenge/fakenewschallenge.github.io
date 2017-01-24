# Fake News Challenge Stage 1 (FNC-I): <br/> Stance Detection
{: .row .col-lg-12 .text-center .section-heading}

<div class='subpanel' markdown="1">

<span class='row' markdown="1">
<div class='col-md-2'></div>

> Fake news, defined by the New York Times as “a made-up story with an intention to deceive” [^1], 
> often for a secondary gain, is arguably one of the most serious challenges facing the news industry today. 
> In a December Pew Research poll, 64% of US adults said that "made-up news" 
> has caused a "great deal of confusion" about the facts of current events [^2].
{: .larger-text .text-left .col-md-8 .pane}



<span class='row' markdown="1">
<div class='col-md-2'></div>
>The goal of the **Fake News Challenge** is to explore how artificial intelligence technologies, 
>particularly machine learning and natural language processing, might be leveraged to combat the fake
>news problem. We believe that these technologies hold promise for significantly 
>automating parts of the procedure human fact checkers employ today to determine if a story is real or a hoax.
{:  .larger-text .text-left .col-md-8}

<span class='row' markdown="1">
<div class='col-md-2'></div>
>But assessing the veracity of a news story is a complex and challenge task, even for trained humans [^3]. 
>So we have decided to break the process into several stages to make it more tractable for ML/NLP/AI algorithms.
>Stage #1 of the **Fake News Challenge (FNC-I)** focuses on the task of 
>Stance Detection -- an important initial step towards automating the process of fact checking.
{:  .larger-text .text-left .col-md-8 .pane}

</div>

<span class='row' markdown="1">
<div class='col-md-2'></div>
>Stance Detection involves estimating the relative perspective (or stance) of two pieces of text relative to an topic, 
>claim or issue. For FNC-1 we have chosen the task of estimating the stance of a body text from a news article relative 
>to a headline. Specifically, the body text may agree, disagree, discuss or be unrelated to the headline.
{:  .larger-text .text-left .col-md-8}

[^1]: https://www.nytimes.com/2016/12/06/us/fake-news-partisan-republican-democrat.html
[^2]: http://www.journalism.org/2016/12/15/many-americans-believe-fake-news-is-sowing-confusion/
[^3]: https://medium.com/factmata/introducing-factmata-artificial-intelligence-for-political-fact-checking-db8acdbf4cf1

### Formal Definition
{: .row .col-lg-12 .text-center .section-heading}

<span class='row' markdown="1">
<div class='col-md-2'></div>

{: .text-left .col-md-8 .pane}
- **Input**
    + A headline and a body text from two news articles.
- **Output**
    + Classify the stance of the body text relative to the claim made in the headline.
    + Four classification categories:
        1. **Agrees**:        The body text agrees with the headline.
        2. **Disagrees**:   The body text disagrees with the headline.
        3. **Discusses**:  The body text discuss the same topic as the headline, but does not take a position
        4. **Unrelated**:    The body text discusses a different topic than the headline

<span class='row' markdown="1">
<div class='col-md-3 tab'></div>

> #### Example headline
> 
> > **“Robert Plant ripped up $800M Led Zeppelin reunion contract”**{: .extra}
> 
>
> * * * 
> 
> #### Example body texts _**without**_ headline
> 
> * * *
>
> > *“Led Zeppelin's Robert Plant turns down £500 MILLION to reform supergroup”*
> 
> ###### &nbsp;&nbsp;&nbsp;&nbsp; Correct classification: **Agree**
>
> * * * 
> 
> > *“No, Robert Plant Didn’t Rip Up an $800 Million Contract”*
>
> ###### &nbsp;&nbsp;&nbsp;&nbsp; Correct classification: **Disagree**
>
> * * * 
> 
> > *“Robert Plant Reportedly Tears Up $800 Million Led Zeppelin Reunion Contract”*
>
> ###### &nbsp;&nbsp;&nbsp;&nbsp; Correct classification: **Discusses**
>
> * * * 
> 
> > *“Richard Branson's Virgin Galactic to launch SpaceShipTwo today”*
> 
> ###### &nbsp;&nbsp;&nbsp;&nbsp; Correct classification: **Unrelated**
{: .text-left .col-md-7 .example-pane}


### Data
{: .row .col-lg-12 .text-center .section-heading}

<span class='row' markdown="1">
<div class='col-md-2'></div>

- #### **Training Set** 
    + ###### [headline : body text] 
    + Pairs of headline and body text with the appropriate class label for each.
- #### Testing Set
    + ###### [headline : body text] 
    + Pairs of headline and body text without class labels used to evaluate systems.
- #### Details 
    + **Release**: The size, location, and structure of the dataset will be announced on Feb 1st, 2017. <br/>
    
    + **Source**: The data is derived from the Emergent Dataset created by Craig Silverman. 
    
    + **Restrictions**: For this stage of the challenge, we require all teams touse only the labeled data supplied by FakeNewsChallenge.org  (i.e. no external data augmentation is allowed).
{: .text-left .col-md-8 .pane}


### Evaluation
{: .row .col-lg-12 .text-center .section-heading}

<span class='row' markdown="1">
<div class='col-md-2'></div>

- Teams will be evaluated based on a weighted, two-level scoring system:

    + **Level 1**: Classify headline and body text as related or unrelated         25% score weighting
    
    + **Level 2**: Classify related pairs as agrees, disagrees, or discusses    75% score weighting
- **Rationale:** The related/unrelated classification task is expected to be much easier and is 
    less relevant for detecting fake news, so it is given less weight in the evaluation metric.
    The stance detection task (classify as agrees, disagrees or discuss) is both more difficult 
    and more relevant to fake news detection, so is to be given much more weight in the 
    evaluation metric
{: .text-left .col-md-8 .pane}


####  Scoring Process Schematic
{: .row .col-lg-12 .text-center .section-heading}

<span class='row' markdown="1">
<div class='col-md-2'></div>

- {:.center}![eval]({{ site.baseurl}}/assets/img/fnc-eval.png)

- Concretely, if a *[headline : body text]*{:.textsc} pair in the test set has the target label unrelated, 
    a team’s evaluation score will be incremented by 0.25 if it labels the pair as unrelated. 

- Otherwise, if the *[headline : body text]*{:.textsc} test pair is related, a team’s score 
    will be incremented by 0.25 if it labels the pair as any of the three classes: 
    *agrees*{:.textsc}, *disagrees*{:.textsc}, or *discusses*{:.textsc}.

- The team’s evaluation score will so be incremented 
    by an additional 0.75 for each related pair if gets the relationship right by labeling 
    the pair with the single correct class: *agrees*{:.textsc}, *disagrees*{:.textsc}, or *discusses*{:.textsc}.
{: .text-left .col-md-8 .whitepane .pane}


### Awards
{: .row .col-lg-12 .text-center .section-heading}

<span class='row' markdown="1">
<div class='col-md-2'></div>


- The top 3 teams with an evaluation score greater than baseline performance will receive cash prizes. 

- The exact amounts and the baseline performance criteria will be announced later.
{: .text-center .larger-text .col-md-8 .pane}