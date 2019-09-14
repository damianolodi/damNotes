---
title: "Probability"
draft: false
---

### Importance

Ability to deal with uncertainty is crucial. This fact is given from the presence of noise in the data returned from every kind of sensor.

-   **Probability allows to quantify uncertainty** using numbers, and after that numbers can be compared.
-   It is usually **not possible to draw conclusions** about whether a particular number was right or wrong **based on a single observation.**

One way to express probability is by using **odds** (the _ratio of the probabilities of an event happening to that of it not happening_)

-   This make it particularly easy to update beliefs when more information becomes available (see below)

* * *

### Bayes Rule

-   _The purpose of the formula is to update the prior odds when new information becomes available, to obtain the posterior odds, or the odds after obtaining the information._ [2]

**Likelihood ratio** &rarr; probability of the observation in case the event of interest (in the above, rain), **divided by** the probability of the observation in case of no event (in the above, no rain).

<img src="/img/content/ai/likelihood-ratio.png" class="img-fluid figure-img img-custom">

Usually the likelihood ration comes from an observation of a new set of events, not considered in the previous odds. [2]

-   In the end, _prior odds_ and _likelihood ratios_ are the same thing, just on two different data sets.

-   The bayes rule says that **posterior odds** = **likelihood ratio** × **prior odds**

* * *

### Bayes Classifier

-   The Bayes classifier is a **machine learning technique** that can be used to **classify objects** such as text documents into two or more classes. The classifier is **trained by analysing a set of training data,** for which the correct classes are given.
    -   _The naive Bayes classifier can be used to determine the probabilities of the classes given a number of different observations._ &rarr; Used in [3] as a naive model to make a spam filter.


-   **Assumption** &rarr; the feature variables are conditionally independent given the class.

* * *

### Resources

1.  [Elements of AI](https://course.elementsofai.com/3/1) — Chapter 3.1
2.  [Elements of AI](https://course.elementsofai.com/3/2) — Chapter 3.2
3.  [Elements of AI](https://course.elementsofai.com/3/3) — Chapter 3.3
