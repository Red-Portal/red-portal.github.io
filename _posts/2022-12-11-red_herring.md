---
layout: post
title: Uncertainty Quantification is the Red Herring of Bayesian Machine Learning
date: 2022-12-11
description: 
tags: Bayes
categories: 
scholar: 
  bibliography: references.bib
  bibliography_template: post_bib
---

### Will Conformal Predictions Replace Bayesian Inference?
With the rise of [conformal predictions](https://www.youtube.com/watch?v=kSGP4F_ZcBY), I hear doubts about the Bayesian approach to machine learning.
This is especially true for Bayesian deep learning, where the Bayesian approach is barely making progress to provide a computationally-feasible baseline for predictive uncertainty quantification.

### Uncertainty Quantification is a Red Herring
The problem I have with these "doubts" about the future of Bayesian machine learning is that they are founded on a false premise.
For me, Bayesian machine learning was never about **predictive** uncertainty quantification.
Okay, maybe the "never" is a bit of a stretch.
But I do feel that there has been too much focus on the predictive uncertainty quantification aspect of Bayesian machine learning that it has completely overtaken the Bayesian cause.

For me, the Bayesian framework provides the following:

* Uncertainty estimates of the *parameters*.
* Uncertainty estimates of the *predictions*.
* Data-driven regularization through marginalization.
* Principled model comparison through Bayes factors.
* Principled (with principles founded on probability theory) model design.
* Decision-theoretic frequentist guarantees.

Uncertainty quantification is just one of these.
Explaining what each bullet exactly means would be too long to qualify as a blog post.
Nevertheless, let me discuss the third point, "Data-driven regularization through marginalization," as I believe it is especially important for machine learning.

### Going Bayesian Improves Accuracy 
In the Bayesian framework, one makes predictions $$p(y \mid \mathcal{D})$$ by marginalizing over the posterior $$p(\theta \mid \mathcal{D})$$ such as
$$
\begin{equation}
  p(y \mid \mathcal{D}) = \int p\left(y \mid \theta\right) \, p\left( \theta \mid \mathcal{D} \right) \, \mathrm{d}\theta.
\end{equation}
$$
Here, $$p(\theta \mid \mathcal{D})$$ automatically takes the *parameter uncertainty* into account, essentially regularizing the prediction.
Thus, assuming the model is sound, fully Bayesian predictions should improve the predictive accuracy compared to naive point estimates.
Personally, whenever a non-Bayesian model receives the Bayesian treatment, I expect the **predictive accuracy to improve**.
In general, I don't care about the predictive uncertainty, I just expect those numbers to go up!

My favorite examples of this are the classic matrix factorization algorithms.
For example, Bayesian principled component analysis {% cite bishop_bayesian_1998 --file references %} and Bayesian non-negative matrix factorization {% cite schmidt_bayesian_2009 --file references %} have shown to be straight upgrades from their original maximum-likelihood variants.
This has also been shown for neural networks by non-other than Radford Neal himself {% cite neal_classification_2006 --file references %}.

For modern deep neural networks, it took some time to figure out whether such improvement could be obtained.
However, with the computational power of Google, Andrew G. Wilson's group has shown that convolutional neural networks achieve better predictive performance {% cite izmailov_what_2021 --file references %}.

### Conclusions
Nonetheless, conformal predictions seem to be a promising approach for obtaining predictive uncertainty estimates.
And this is fine; Bayesian machine learning has its unique agenda.
So keep drinking the Bayesian Kool-Aid!


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
