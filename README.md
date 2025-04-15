# ADoBo — Automatic Detection of Borrowings 


## What is ADoBo 2025?
ADoBo is the shared task on **automatic detection of borrowings**, that is, automatically retrieving words from one language that are incorporated into another language (see [What is lexical borrowing?](https://adobo-task.github.io/borrowing.html)). In 2025 we are holding the second edition of ADoBo at [IberLEF 2025](https://sites.google.com/view/iberlef-2025/). The first edition was held in [2021](https://adobo-task.github.io/2021.html).

The task will run from **April 2025 to June 2025** and is part of [IberLEF 2025](https://sites.google.com/view/iberlef-2025/), which will take place in September 2025 in Zaragoza, Spain.
 

[Stay tuned](mailto:adobo-task@googlegroups.com) for more information about the task.

## The 2025 task 
For this second edition of ADoBo we propose a shared task on retrieving **anglicisms** from Spanish text, i.e. [words borrowed](https://adobo-task.github.io/borrowing.html) especifically from English that have recently been imported into the Spanish language (words like _running_, _smartwatch_, _influencer_ or _youtuber_).  


The test set will consist of a collection of sentences written in European Spanish from the journalistic domain. Participants will be required to run their systems on the given sentences and return the anglicism spans in the sentence. For example, given the sentence: 

```
"Al no tener equipo de ventas, ni 'country managers' ni hacer mucho marketing, no tenemos grandes costes."

```

The correct output should be: 

```

"Al no tener equipo de ventas, ni 'country managers' ni hacer mucho marketing, no tenemos grandes costes.";country managers;marketing

```


There is no official training set for ADoBo 2025 task. On the contrary, participants are allowed to use _any_ available resource they may want to use to create their models: dictionaries, lexicons, existing datasets, etc. (including [the COALAS dataset from the 2021 shared task](https://github.com/lirondos/coalas)). 


All flavours of anglicism detection systems are welcome: rule-based approaches, classic machine learning, deep learning, generative models, etc. We encourage participants to explore any LLMs they wish for this task. The more varied the systems proposed are, the more we will learn about the task.   

> **The 2021 edition of ADoBo shared task consisted in retrieving both anglicisms (which were labeled as ENG) as well as other lexical borrowings originated in other languages (labeled as OTHER) using BIO format. For the 2025 shared task we are framing the problem as a span-based task (the expected output is a span of text) and we are focusing *exclusively* on retrieving anglicisms. We advise participants to bear this in mind if they reuse any of the available resources from the 2021 edition.**



## Dataset
The dataset for ADoBo 2025 will consist of a collection of sentences from the journalistic domain written in European Spanish. Each sentence in the dataset may contain one anglicism, several anglicisms or none.

The dev set will be released on **April 21**. The test set will be released on **May 6th**.

## Evaluation
The evaluation for ADoBo 2025 shared task  is **span based evaluation**. This means that the expected output is a span of text, not BIO-encoded token annotations (unlike the 2021 edition). The CSV format that the scoring script expects is semicolon separated values: 

```
sentence;span1;span2;span3;etc
```

The scoring script makes the following assumptions: 

* Casing of the output span is disregarded (_SMARTWATCH_ and _smartwatch_ will both match, regardless of which way it was written in the input sentence).

* Trailing quotation marks in the output span are disregarded (_"smartwatch"_ and _smartwatch_ will both match, regardless of which way it was written in the input sentence).

* If the same span appears twice in the sentence, it suffices for it to appear once in the output to be considered a match.

These assumptions are made in order to accommodate the participation of LLM-based solutions to the task.


## Tentative Schedule


* April 21: Dev set released.
* May 6: Test set released.
* May 19: Systems output submissions.
* May 26: Results posted and Test set with GS annotations released.
* June 2: Working notes paper submission.
* June 16: Notification of acceptance (peer-reviews).
* June 23: Camera ready paper submission.
* September: ADoBo session at IberLEF 2025.


## How to participate?
Information about how to join the shared task will be posted on this website and on the Google group at [adobo-task[@]googlegroups.com](mailto:adobo-task@googlegroups.com)

## Additional info 
* [Annotation guidelines can be found here](https://adobo-task.github.io/docs/guidelines.pdf).
* [What is lexical borrowing?](https://adobo-task.github.io/borrowing.html)


## Organization Committee

* [Elena Álvarez-Mellado](https://lirondos.github.io/), Universidad Nacional de Educación a Distancia (UNED).
* [Julio Gonzalo Arroyo](https://sites.google.com/view/nlp-uned/people/julio-gonzalo), Universidad Nacional de Educación a Distancia (UNED).
* [Constantine Lignos](https://lignos.org/), Brandeis University.
* Jordi Porta-Zamorano, Universidad Autónoma de Madrid (UAM).

## Contact

* Participants are encouraged to ask any questions through: [adobo-task[@]googlegroups.com](mailto:adobo-task@googlegroups.com)

* Elena Álvarez Mellado [ealvarezmellado[@]gmail.com](mailto:adobo-task@googlegroups.com)


[Back to ADoBO home](https://adobo-task.github.io/)