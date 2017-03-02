# Fake News Challenge Stage 1 (FNC-I): <br/> Stance Detection
{: .row .col-lg-12 .text-center .section-heading}

<div class='subpanel text-left' markdown="1">

<span class='row' markdown="1">
<div class='col-md-2'></div>
> Fake news, defined by the New York Times as "a made-up story with an intention to deceive" [^1],
> often for a secondary gain, is arguably one of the most serious challenges facing the news industry today.
> In a December Pew Research poll, 64% of US adults said that "made-up news" has caused a "great deal of confusion"
> about the facts of current events [^2].
{: .larger-text .text-left .col-md-8 .pane}



<span class='row' markdown="1">
<div class='col-md-2'></div>
> The goal of the **Fake News Challenge** is to explore how artificial intelligence technologies, particularly machine learning
> and natural language processing, might be leveraged to combat the fake news problem. We believe that these AI technologies 
> hold promise for significantly automating parts of the procedure human fact checkers use today to determine if a story 
> is real or a hoax.
<div class='col-md-2'></div>
> Assessing the veracity of a news story is a complex and cumbersome task, even for trained experts [^3]. Fortunately, 
> the process can be broken down into steps or stages. A helpful first step towards identifying fake news is to 
> understand what other news organizations are saying about the topic. We believe automating this process, called 
> **Stance Detection**, could serve as a useful building block in an AI-assisted fact-checking pipeline. So stage #1 of 
> the **Fake News Challenge (FNC-1)** focuses on the task of Stance Detection.



<div class='col-md-2'></div>
> Stance Detection involves estimating the relative perspective (or stance) of two pieces of text relative to a topic, 
> claim or issue. The version of Stance Detection we have selected for FNC-1 extends the work of Ferreira & Vlachos [^4]. 
> For FNC-1 we have chosen the task of estimating the stance of a body text from a news article relative to a headline. 
> Specifically, the body text may agree, disagree, discuss or be unrelated to the headline. 
</div>

{:  .larger-text .text-left .col-md-8}

[^1]: [New York Times. "As Fake News Spreads Lies, More Readers Shrug at the Truth"](https://www.nytimes.com/2016/12/06/us/fake-news-partisan-republican-democrat.html)
[^2]: [Pew Research Center. "Many Americans Believe Fake News Is Sowing Confusion"](http://www.journalism.org/2016/12/15/many-americans-believe-fake-news-is-sowing-confusion/)
[^3]: [Dhruv Ghulati, Co-Founder, Factmata. "Introducing Factmata—Artificial intelligence for automated fact-checking"](https://medium.com/factmata/introducing-factmata-artificial-intelligence-for-political-fact-checking-db8acdbf4cf1)
[^4]: [William Ferreira and Andreas Vlachos, "Emergent: a novel data-set for stance classification"](http://aclweb.org/anthology/N/N16/N16-1138.pdf)

### Formal Definition
{: .row .col-lg-12 .text-center .section-heading}

<span class='row' markdown="1">
<div class='col-md-2'></div>

{: .text-left .col-md-8 .pane}
- **Input**
    + A headline and a body text - either from the same news article or from two different articles.
- **Output**
    + Classify the stance of the body text relative to the claim made in the headline into one of four categories:
        1. **Agrees**:        The body text agrees with the headline.
        2. **Disagrees**:   The body text disagrees with the headline.
        3. **Discusses**:  The body text discuss the same topic as the headline, but does not take a position
        4. **Unrelated**:    The body text discusses a different topic than the headline

<span class='row' markdown="1">
<div class='col-md-3 tab'></div>

> #### Example headline
> 
> > **"Robert Plant Ripped up $800M Led Zeppelin Reunion Contract"**{: .extra}
> 
>
> * * * 
> 
> #### Example snippets from body texts and correct classifications
> 
> * * *
>
> > *"... Led Zeppelin's Robert Plant turned down £500 MILLION to reform supergroup. ..."*
> 
> ###### &nbsp;&nbsp;&nbsp;&nbsp; Correct classification: **Agree**
>
> * * * 
> 
> > *"... No, Robert Plant did not rip up an $800 million deal to get Led Zeppelin back together. ..."*
>
> ###### &nbsp;&nbsp;&nbsp;&nbsp; Correct classification: **Disagree**
>
> * * * 
> 
> > *"... Robert Plant reportedly tore up an $800 million Led Zeppelin reunion deal. ..."*
>
> ###### &nbsp;&nbsp;&nbsp;&nbsp; Correct classification: **Discusses**
>
> * * * 
> 
> > *"... Richard Branson's Virgin Galactic is set to launch SpaceShipTwo today. ..."*
> 
> ###### &nbsp;&nbsp;&nbsp;&nbsp; Correct classification: **Unrelated**
{: .text-left .col-md-7 .example-pane}


### Data
{: .row .col-lg-12 .text-center .section-heading}

<span class='row' markdown="1">
<div class='col-md-2'></div>

- #### **Training Set** 
    + ###### [headline, body text, label] 
    + Pairs of headline and body text with the appropriate class label for each.
- #### Testing Set
    + ###### [headline, body text] 
    + Pairs of headline and body text without class labels used to evaluate systems.
- #### Details 
    + **Data**: The dataset and a brief description of the data is provided at the [FNC-1 github](https://github.com/FakeNewsChallenge/fnc-1).  <br/>
    
    + **Source**: The data is derived from the Emergent Dataset created by Craig Silverman. 
{: .text-left .col-md-8 .pane}


### Rules
{: .row .col-lg-12 .text-center .section-heading}

<span class='row' markdown="1">
<div class='col-md-2'></div>

- ##### Rule #1 
    + For this stage of the challenge, we require all teams to use only the labeled data supplied by FakeNewsChallenge.org  (i.e. no external data augmentation is allowed). See also [FAQ]({{ site.baseurl}}/#faq) section.
- ##### Rule #2
    + All winning teams must be willing to open source their solutions/systems.
- ##### Rule #3 
    + Have fun!
{: .text-left .col-md-8 .pane}

### Evaluation
{: .row .col-lg-12 .text-center .section-heading}

<span class='row' markdown="1">
<div class='col-md-2'></div>

- Teams will be evaluated based on a weighted, two-level scoring system:

    + **Level 1**: Classify headline and body text as *related* or *unrelated*         25% score weighting
    
    + **Level 2**: Classify related pairs as *agrees*, *disagrees*, or *discusses*    75% score weighting
- **Rationale:** The related/unrelated classification task is expected to be much easier and is 
    less relevant for detecting fake news, so it is given less weight in the evaluation metric.
    The Stance Detection task (classify as agrees, disagrees or discuss) is both more difficult 
    and more relevant to fake news detection, so is to be given much more weight in the 
    evaluation metric
{: .text-left .col-md-8 .pane}


####  Scoring Process Schematic
{: .row .col-lg-12 .text-center .section-heading}

<span class='row' markdown="1">
<div class='col-md-2'></div>

- {:.center}![eval]({{ site.baseurl}}/assets/img/fnc-eval.png)

- Concretely, if a *[headline, body text]*{:.textsc} pair in the test set has the target label *unrelated*, 
    a team’s evaluation score will be incremented by 0.25 if it labels the pair as unrelated. 

- If the *[headline, body text]*{:.textsc} test pair is related, a team’s score 
    will be incremented by 0.25 if it labels the pair as any of the three classes: 
    *agrees*, *disagrees*, or *discusses*.

- The team’s evaluation score will so be incremented 
    by an additional 0.75 for each related pair if gets the relationship right by labeling 
    the pair with the single correct class: *agrees*, *disagrees*, or *discusses*.
{: .text-left .col-md-8 .pane}

### Baseline
{: .row .col-lg-12 .section-heading}

<span class='row' markdown="1">
<div class='col-md-2'></div>

- A simple baseline using hand-coded features and a GradientBoosting classifier is available on <a href="https://github.com/FakeNewsChallenge/fnc-1-baseline" target="_blank">Github</a>.

- The baseline implementation also includes code for pre-processing text, splitting data carefully to avoid bleeding of articles between training and test, k-fold cross validation, scorer, and most of the crud you will need to write to experiment with this data. The hand-crafted features word/ngram overlap features, and indicator features for polarity and refutation. 

- With these features and a gradient boosting classifier, the baseline achieves a weighted accuracy score of **81.19%** (as per the evaluation scheme described above) with a 10-fold cross validation.  The baseline is for simply for your reference. You are welcome to use it any way you like it (or not).
{: .text-left .col-md-8 .pane}

### Awards
{: .row .col-lg-12 .section-heading}

<span class='row' markdown="1">
<div class='col-md-2'></div>


- The top 3 teams with an evaluation score greater than baseline performance on test data will receive cash prizes. 

- The exact amounts and the baseline performance criteria will be announced later.
{: .text-left .larger-text .col-md-8 .pane}
