---
title: "On Bias and Fairness in NLP: How to have a fairer text classification?"
collection: publications
type: "Pre-print"
date: 2023-05-31
authors: "Fatma Elsafoury, Stamos Katsigiannis, and Naeem Ramzan"
venue: "arxiv"
#venue-url: "https://coling2022.org/"
#proceedings: "Proceedings of the 29th INTERNATIONAL CONFERENCE ON COMPUTATIONAL LINGUISTICS"
#paperurl: '/files/publications/2022/SOS_2022/SOS_bias_paper.pdf'
#bibtexurl: '/files/publications/2022/SOS_2022/bib.bib'
---
<a href="https://arxiv.org/abs/2305.12829"><img src="/images/paper_symbol.png" alt="Link to paper" style="width:42px;height:42px;"></a>


**Abstract:** In this paper, we provide a holistic analysis of the different sources of bias, Upstream, Sample and overamplification biases, in NLP models. We investigate how they impact the fairness of the task of text classification. We also investigate the impact of removing these biases using different debiasing techniques on the fairness of text classification. We found that overamplification bias is the most impactful bias on the fairness of text classification. And that removing overamplification bias by fine-tuning the LM models on a dataset with balanced representations of the different identity groups leads to fairer text classification models. Finally, we build on our findings and introduce practical guidelines on how to have a fairer text classification model.