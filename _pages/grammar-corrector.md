---
defaults:
  # _pages
  - scope:
      path: ""
      type: pages
layout: splash
permalink: /projects/grammar-corrector
author_profile: false
page.title: Grammar Corrector
---


## Context

[Talentica](https://www.talentica.com/what-we-do/) works closely with startups: from the ideation phase to product release and multiple rounds fundings. \\
Our client, an eCommerce store selling a niche catalog wanted a grammar correction tool for their product description. This description was written by sellers across 235+ countries, most of whom were non-native English speakers. 

## My journey

Worked in close collaboration with product owner and external researchers. Being the only researcher from Talentica, I had a lot of freedom to manage the project and drive the direction of research.


### Reviewing existing solutions
Rule-based engines work well with documented and syntactic errors, but
there wern't many visible patterns for the grammatical mistakes in the corpus.
Few services performed well but weren't a feasible option for the clients.

### Preparing labelled dataset
The corpus from the client website wasn't _labelled_. The [benchmark dataset](https://www.comp.nus.edu.sg/~nlp/corpora.html) available was not large enough to train my models. We used external services to identify the grammatically correct data. This data was further processed using tokenizers to label it in accordance with the benchmark dataset.

### Statistical NLP
Failure to identify the subtleties of errors in non-native speakers by rule-based engines, the next logical step
was to implement stastical libraries for NLP. I implemented n-gram models using nltk, inspired by the Stanford's [stastistical language parser](https://nlp.stanford.edu/software/lex-parser.shtml).

### Generating synthetic dataset
Since deep learning requires an enormous amount of labelled dataset to train, I had to artificially generate my training data. I used a [movie dialog corpus](http://www.cs.cornell.edu/~cristian/Cornell_Movie-Dialogs_Corpus.html) and programatically introduced certain perturbations.

### Exploring deep learning
Working ahead of my schedule, I planned on exploring deep learning solution via TensorFlow. I implemented an RNN that resembled my previously developed model of n-grams. This approach gave better results on particular contextual errors but wasn't viable option overall.

### Evaluating results
Evaluated the implemented results using AUC-ROC curves. I did further qualitative analysis on the results by filtering out the _unacceptable_ grammatical errors. Stastical language parser was the clear winner for our use case.
