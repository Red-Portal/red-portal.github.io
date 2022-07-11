---
layout: post
title: Was Charles Stein a Bayesian?
date: 2022-07-11
description: 
tags: Bayes
categories: 
#comments: true
scholar: 
  bibliography: references.bib
  bibliography_template: post_bib
---

I recently contracted COVID (probably while watching the Rolling Stones perform at Hyde Park...) and therefore had to self-isolate.
During this time, I was curious whether the legendary [Charles M. Stein (1920-2016)](https://en.wikipedia.org/wiki/Charles_M._Stein) was a Bayesian, given his huge contribution to Bayesian statistics and machine learning.

## Charles Stein and The Bayesians
Although I do not consider myself to be a statistician, I regularly read statistics papers in order to renew my Bayesian membership card. (If anybody is wants to register too, please send me an email.)
And Charles Stein has made various important contributions to the Bayesian cause.

### James-Stein Estimator
For example, the [James-Stein estimator](https://en.wikipedia.org/wiki/James%E2%80%93Stein_estimator) {% cite stein_inadmissibility_1956 --file references %}, although not directly a Bayesian idea, has a nice empirical Bayesian {% cite efron_stein_1973 --file references %} interpretation.
(This would be part of a [running joke](https://www.inference.vc/everything-that-works-works-because-its-bayesian-2/) that Bayesians tend to claim anything that works is actually a Bayesian method in disguise.)
In more detail, James-Stein estimator has shown that some types of *biased* estimators can have quite dramatically less error than the maximum likelihood estimator under certain loss functions.
This has directly motivated all kinds of regularized/shrinkage estimators.

James-Stein estimator was apparently a big surprise to the statisticias back in the day.
Even [Michael M. Jordan](https://youtu.be/EYIKy_FM9x0?t=4931) mentioned it to be "mysterious and beautiful".

### Stein's Method
The contribution of Stein that I'm perhaps the most used to, is [Stein's method](https://en.wikipedia.org/wiki/Stein%27s_method) {% cite stein_bound_1972 --file references %}.
Stein method is a way to measure the difference between two distributions with respect to an arbitrary function in the form of

$$
\begin{equation}
	d\left(p, q\right) = \sup_{f \in \mathcal{H}} \left| \int f\,dp - \int f\,dq \right|.
\end{equation}
$$

This generalizes many other classic distance measures such as total variation.
The key element is the freedom to choose $$f \in \mathcal{H}$$.

While Stein's method has been a textbook (or more exactly, graduate-level mathematical statistics textbook) thing for some time, it recently sparked new interest.
Mainly, Stein variational {% cite liu_stein_2016 --file references %} methods (or more generally variational particle methods) and kernelized discrepancies {% cite gorham_measuring_2015 --file references %}.
Both of these have created their own fields and have now become active, promising lines of research that are in the heart of Bayesian front.
(An interesting trivia is that Gorham and Mackey originally [implemented](https://github.com/jgorham/SteinDiscrepancy.jl) their method in an early version of Julia.)

## Was Charles Stein a Bayesian?
During self-isolation, I stumbled upon this paper called [A Conversation with Charles Stein](https://www.jstor.org/stable/2245793?seq=1) {% cite degroot_conversation_1986 --file references %}, which is more or less a transcript of an interview with Charles Stein by Morris DeGroot (also a very famous statistician), that was published in Statistical Science.
The interview has been published in 1986, which seems to be around Charles Stein retired, but amazingly enough, Charles lived until 2016!

### An Interview Published in an Academic Journal?
One thing that I admire about the statisticians is that they are much less narrow-viewed on what constitutes an academic paper.
Both computer science (CS) and electronics engineering (EE) tend to have a very rigid in comparison.
Statisticians tend to publish opinion pieces, rants, and even interviews! in their journals, which cannot be imagined in CS and EE.
Academic publishing initially started from hand written letters, which shows the sole purpose of academic papers: communicating ideas and discoveries.
After all, many academic journals are, in principle, magazines (hence the prestigious [IEEE Signal Processing Magazine](https://signalprocessingsociety.org/publications-resources/ieee-signal-processing-magazine)) or a collection of correspondances (hence the name "transactions" or "letters").
As long we can convey some form of intellectual value, I hope we could employ diverse ways of communication, not just the stereotypical "introduction-background-method-experiment-conclusion".

### Was Charles Stein a Bayesian?

> **DeGroot**: Since you brought up the subject, what is your view of the Bayesian philosophical framework?
> 
> **Stein**: Well, it's rather negative. Of course a lot of good work has been done by people from that point of view. 
> But basically the Bayesian point of view is often accompanied by an insistence that people ought to agree to a certain doctrine, even without really knowing what that doctrine is. 
> For example, would you be able to specify to me what you would consider an authoritative presentation of the Bayesian view that we are so often approached to accept

It is not clear to me *which* doctrine Charles is talking about.
But I would argue that the frequentist framework also involves lots of doctrines (also known as *assumptions*).
But it's true that the frequentist doctrines are, in general, much less controversial if you come from certain backgrounds.
For example, it is easier to assume that the "true" parameter exists, rather than to admit that there is no such thing.

> **DeGroot**: Well, I'm not being interviewed. [Laughs] I could put in a plug for my book on Bayesian decision theory that gives an axiomatic system for probability and utility theory which together imply the entire decision-making process. 
> I mean, normatively anyway.
>
> **Stein**: Yes, but of course that is the thing. 
> One is asked to accept something normatively before one knows what that thing really is, rather than the attitude that we have toward other systems where we set out axioms or definitions and use them for the purpose of developing a system, and then if the system turns out to be interesting we pursue this. 
> But we never ask whether those axioms are true or not; rather, we ask if we can find instances in which this axiomatic development is useful. 
> If so, we accept it. In particular, we try to judge the consequences. 
> Whereas, as you know, there are grave difficulties in trying to apply the Bayesian notions to interesting problems because of the difficulty of choosing a prior distribution. 
> There is one point of view specified by Jeffreys who seems to be saying that there is a prescription, which he did not invent but which he seems to endorse, for choosing a (usually improper) prior distribution, and that simply does not work in general.
> The alternative is that the choice of a prior distribution must be made subjectively, and that I find completely inappropriate.
> Well, what can one say? Of course, statistical decision theory gives us, within a certain class of problems, an indication of how prior distributions do enter statistics from another point of view. 
> And so in some ways the difference between Wald's decision-theoretic approach and the Bayesian approach is small.

From this, we can clearly see that Charles Stein has the classic critical frequentist view on the Bayesian approach.
However, we have to consider that the fundamentals of Bayesian theory only started to mature in the 90s and this interview took place way before that.
Plus, the Bayesian framework has now established lots of connections with the frequentist framework (whether that is the appropriate attitude is, interestingly, quite a controversial subject).
Furthermore, using subjective priors has been shown to be sensible as long as the model is evaluated objectively and extensively {% cite gelman_bayesian_2020a --file references %}.

I find the point about prior selection, however, still a valid critism.
Although some people treat prior selection to be a "solved problem", in practice, it is still a very difficult subject that needs lots of work on a problem-by-problem basis.
Fortunately, many are working on principled procedures for eliciting subjective informative priors {% cite mikkola_prior_2021 --file references %} and designing priors with good frequentist properties {% cite consonni_prior_2018 --file references %}.
But, we need to mind that frequentist methods equally involve "manual work" to establish frequentist guarantees on a method-by-method basis.
Therefore, on a practical note, neither is less difficult than the other.

An interesting bit is the comment on what we now call Jeffreys priors.
They are known to ocassionally mess up model comparison with Bayes factors, which I believe is what Charles Stein is discussing here. 
(Please let me know if you think he is talking about a different aspect of Jeffreys priors.)

> **DeGroot**: Because Wald used priors as a technical device for determining optimal procedures.
>
> **Stein**: Yes, and therefore we are considering the same procedures. Roughly speaking, the basic theorems of decision theory say that in some sense good procedures and Bayes procedures are very much the same thing. 
> This is, of course, a gross over simplification, but it does enable us to understand how prior distributions come in.

Interestingly, it seems that Charles Stein is sympathetic to (possibly subjective) Bayesian approaches when coming from a decision-theoric perspective.

> **DeGroot**: Let's talk about probability for a moment. You say that the notion of subjective probability is unacceptable to you. 
> What definition of probability do you use?
>
> **Stein**: Essentially Kolmogorov's. That it is a mathematical system.
>
> **DeGroot**: Simply any set of numbers that satisfies the axioms of the calculus of probabilities.
>
> **Stein**: Yes.
>
> **DeGroot**: But what do these numbers represent in the real world?
>
> **Stein**: Well, there is no unqiue interpretation.
> And of course I'm talking about Kolmogorov's old interpretation of probability and not the complexity interpretation. 
> In his book he mentions briefly two aspects of the interpretation. The first is the traditional relative frequency of occurrence in the long run.
> And the second is that when one puts forward a probabilistic model that is to be taken completely seriously for a real world phenomenon, then one is asserting in principle that any single specified event having very small probability will not occur. 
> This, of course, combined with the law of large numbers, weak or strong, really is a broader interpretation than the frequency notion. 
> So, in fact, the frequency interpretation in that sense is redundant. 
> This doesn't answer the question, "When I say the probability is 1/6 that this die will come up 6 on the next toss, what does that statement mean?" 
> But then in no serious work in any science do we answer the question, "What does this statement mean?" It is an erroneous philosophical point of view that leads to this sort of question.

I find this comment from Charles Stein quite surprising.
After all, Science has branched out of philosophy, and there is therefore no reason to shy away from philosophical questions and philosophical point of views.
In fact, philosophical discussions are scattered everywhere in the history of science.
I always thought that statistics was science more than mathematics (therefore some statistics departements prefer to call themselves statistical science).
From this perspective, perhaps Charles Stein considered him to be more of a mathematician than a statistican.

> **DeGroot**: But surely that means that there is a subjective element entering into the development of the models and the numerical probabilities.
>
> **Stein**: But, you see, that's something very different from saying that one is absolutely never permitted to consider a probabilistic model in which anything is unknown, and that is the strict interpretation of the Bayesian point of view. 
> Some statisticians seem to try to accept this point of view as sort of a philosophical position but to deny it in practice, which is not reasonable.

This comment is interesting because, in practice, it is very rare to encounter a problem where absolutely no prior information is available.
Often times (or rather, all the time) we at least have an idea about the support or the extreme values of the data.
And even this much information is pretty useful as far as prior information goes.

> **DeGroot**: Do you think your political views influence the kind of problems you work on and your scientific philosophy at all, or are they separate?
>
> **Stein**: I'd say they are largely separate. Of course, I don't do military work, not even nominally. That is, I haven't been on a military contract for 18 years.
>  Actually, even before that it was distasteful but I allowed myself to be talked into it. But this is a hard  question to answer.
> I would admit that my work is largely independent of my political attitudes. 
> I don't agree with Lindley that a subjective approach to probability is a consequence of being a Marxist or socialist.

Lindley would be surprised to know how much ground the "Marxists" have gained to this day.
But seriously, interesting to know that Lindley thought this way.

> **Stein**: Yes. I may want to modify some of my answers when I see the transcript of this conversation.
> Somehow I don't seem to think along the same lines as other people, which is useful. It's good that different  people think differently.
>
> **DeGroot**: Thank you, Charles

Indeed, speaking and listening to each others' opinion freely without prejudice is becoming more and more difficult.
I believe different opinions are especially valuable since they broaden one's view.
It is ironic that, on this day and age where everyone is connected in the speed of light, echochambers and self-reinforcement of opinions is becoming a bigger problem, especially in my home country South Korea.

## Conclusions

From this nice interview by DeGroot, I could see how Charles Stein, and probably many well respected statistians of that day, thought of Bayesian approaches.
I would be interested to know whether Charles Stein actively worked after this interview.
Unfortunately, after a quick search, I couldn't find a complete bibliogrphay of Charles Stein's.

References
----------
{% bibliography --cited %}

<script src="https://utteranc.es/client.js"
        repo="Red-Portal/red-portal.github.io"
        issue-term="title"
        theme="preferred-color-scheme"
        crossorigin="anonymous"
        async>
</script>
