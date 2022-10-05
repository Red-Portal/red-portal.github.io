---
layout: post
title: Being Schmidhubered on Deep Learning and Flat Minimas
date: 2022-10-04
description: 
tags: DL
categories: DL
scholar: 
  bibliography: references.bib
  bibliography_template: post_bib
---

Until very recently, the incredible generalization capabilities of deep neural networks have been attributed to *flat minimas*.
That is, "flat minimas" generalize better because of the intuitive explanation that flatter minimas are more robust to perturbation (train dataset sampling).
For some time, this discovery has been attributed to {% cite keskar_largebatch_2017 --file references %}, often accompanying their sketch of the intuition.

Although this "intuitive" explanation has been somewhat scientifically disputed multiple times until now.
I do not now where the scientific concensus is now on this subject.
Because of this, I have never got too deep into this topic, and I only knew the attribution to Keskar *et al.*
However, it turned out that J. Schmidhuber and S. Hochreiter came up with this idea in... 1994!
Hell, they even have a paper named "Flat minima" {% cite hochreiter_flat_1997 --file references %}.
Even better, one of their paper on the topic had been presented at NIPS'94 {% cite hochreiter_simplifying_1994 --file references %}.
To me personally, this sets a whole new standard on being *Schmidhubered*...
(Fortunately though, the two papers by Schmidhuber co. did and still do get properly cited.)

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
