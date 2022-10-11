---
title: "Does BERT Pay Attention To Cyberbullying?"
collection: publications
type: "Conference Short Paper"
date: 2021-07-11
authors: "Fatma Elsafoury, Stamos Katsigiannis, Steven R. Wilson, and Naeem Ramzan"
venue: "SIGIR 2021"
venue-url: "https://sigir.org/sigir2021/"
proceedings: "Proceedings of the 44th International ACM SIGIR Conference on Research and Development in Information Retrieval sigir 2021"
#paperurl: '/files/publications/2021/sigir_2021.pdf'
poster: '/files/publications/2021/Sigir_2021_Poster.pdf'
presentation: '/files/publications/2021/sigir_presentation.pdf'
bibtexurl: '/files/publications/2021/sigir.bib'
---
<a href="/files/publications/2021/sigir_2021.pdf"><img src="/images/paper_symbol.png" alt="Link to paper" style="width:42px;height:42px;"></a>
<a href="/files/publications/2021/Sigir_2021_Poster.pdf"><img src="/images/poster_symbol.png" alt="Link to poster" style="width:42px;height:42px;"></a>
<a href="https://github.com/efatmae/Does-BERT-pay-attention-to-cyberbullying-/tree/main/Does-BERT-pay-attention-to-cyberbullying-"><img src="/images/github_symbol.png" alt="Link to code" style="width:42px;height:42px;"></a>


**Abstract:** Social media have brought threats like cyberbullying, which can
lead to stress, anxiety, depression and in some severe cases, suicide
attempts. Detecting cyberbullying can help to warn/ block bullies
and provide support to victims. However, very few studies have
used self-attention-based language models like BERT for cyberbul-
lying detection and they typically only report BERT’s performance
without examining in depth the reasons for its performance. In
this work, we examine the use of BERT for cyberbullying detec-
tion on various datasets and attempt to explain its performance by
analysing its attention weights and gradient-based feature impor-
tance scores for textual and linguistic features. Our results show
that attention weights do not correlate with feature importance
scores and thus do not explain the model’s performance. Addi-
tionally, they suggest that BERT relies on syntactical biases in the
datasets to assign feature importance scores to class-related words
rather than cyberbullying-related linguistic features.