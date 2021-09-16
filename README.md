# ADoBo — Automatic Detection of Borrowings 

## Results of ADoBo 2021
Results of ADoBo shared task 2021 can be checked out on the following publications: 

### Participating systems
- _[The futility of STILTs for classification of lexical borrowings in Spanish](http://ceur-ws.org/Vol-2943/adobo_paper2.pdf)_, Javier de la Rosa  
- _[Detection of Borrowings in the Spanish Language Using Pseudo-label Technology](http://ceur-ws.org/Vol-2943/adobo_paper1.pdf)_, Shengyi Jiang, Tong Cui, Yingwen Fu, Nankai Lin and Jieyi Xiang

### Task overview
- _[Overview of ADoBo 2021: Automatic Detection of Unassimilated Borrowings in the Spanish Press](http://journal.sepln.org/sepln/ojs/ojs/index.php/pln/article/view/6396)_, Elena Álvarez Mellado, Luis Espinosa Anke, Julio Gonzalo Arroyo, Constatine Lignos, Jordi Porta Zamorano




## ADoBo session at IberLEF 2021
We will be holding a session on ADoBo as part of [IberLEF 2021 workshop](https://sites.google.com/view/iberlef2021/workshop). The session will happen on **September 21st at 11.00am-12.30 (CEST)** and will be held online. 

**[More information on ADoBo session here](https://adobo-task.github.io/schedule.html)**

## What is ADoBo?
ADoBo is the shared task on **automatic detection of borrowings**. For the first edition of ADoBo, we propose a shared task on detecting direct, unadapted, emerging borrowings in the Spanish press, i.e. detecting lexical borrowings that appear in the Spanish press and that have recently been imported into the Spanish language (words like _running_, _smartwatch_, _influencer_ or _youtuber_). Participants will be provided a corpus of Spanish newswire annotated with lexical borrowings, and will have to create  systems that can automatically detect lexical borrowings from Spanish newswire.

[[What is a lexical borrowing? Why is borrowing detection an interesting task?]](https://adobo-task.github.io/borrowing.html)

The task will run from **February 2021 to June 2021** and is part of [IberLEF 2021](https://sites.google.com/view/iberlef2021/), which will take place in September 2021 in Spain.

## Dataset
A corpus of Spanish newswire will be distributed among participants. The articles will be annotated with **direct, unadapted, emerging lexical borrowings**, i.e. lexical borrowings that have been imported into Spanish language and that haven't been assimilated yet (words such as _look_, _hype_, _cliffhanger_ or _lawfare_). [Annotation guidelines can be found here](https://adobo-task.github.io/docs/guidelines.pdf).

Borrowings will be annotated with BIO labels with two possible categories: ``ENG`` for English borrowings and ``OTHER`` for lexical borrowings from other languages (non lexical borrowings will have the tag ``O``). Only unadapted lexical borrowings will be considered. This means that borrowings that have already gone through orthographical or morphological adaption (such _fútbol_ or _hackear_) will not be labeled as borrowings. 

```
El O
escándalo O
de O
las O
tarjetas O
' O
black B-ENG
' O
```

Participants will be provided with annotated versions of the training and development set, and an unannotated test set. Participants are expected to submit the annotated test set produced by their system. 

[A sample set](https://github.com/adobo-task/adobo-2021/tree/main/corpus) has been made available. The purpose of this sample set is for participants to get familiar with the dataset format.

## Evaluation
Submissions will be evaluated using the standard precision, recall and F1 over spans:
* **Precision**: The percentage of borrowings in the system’s output that are correctly recognized and classified.
* **Recall**: The percentage of borrowings in the test set that were correctly recognized and classified.
* **F1-measure**: The harmonic mean of Precision and Recall.

F1-measure will be used as the oﬀicial evaluation score, and will be used for the final ranking of the participating teams. 

It should be noted that the evaluation for the final ranking will be done exclusively at the **span level**. This means that only full matches will be considered, and no credit will be given to partial matches, i.e. given the multitoken borrowing _late night_, the entire phrase would have to be correctly labeled in order to count as a true positive. 

### Scoring your output

The precision, recall, and F1 metrics will be computed using [SeqScore](https://github.com/bltlab/seqscore), a new Python package for sequence labeling evaluation.
It works similarly to the classic `conlleval.pl` scorer and the `seqeval` package in that it decodes BIO labels in a way that tolerates some improper sequences (for example, starting an entity with I- instead of B-).

To evaluate your output, simply install (or upgrade) SeqScore as follows: `pip install -U seqscore`.
Once it's installed, you can call it from the command line as the main script has been installed in your Python environment.

If the reference (annotation) is located at `dev.conll` and your predictions are located at `output.conll`, you would simply run `seqscore score output.conll --reference dev.conll`.

The output will look like this:
```
| Type   |   Precision |   Recall |     F1 |   Reference |   Predicted |
|--------|-------------|----------|--------|-------------|-------------|
| ALL    |      100.00 |   100.00 | 100.00 |           7 |           7 |
| ENG    |      100.00 |   100.00 | 100.00 |           7 |           7 |
```

You can change the format of the output by using the `--display` flag, for example `--display delim` will get you a tab-delimited version of that table (you can configure the delimiter using the `--delim` flag).

Scoring can only be performed on BIO encoded output. However, as we continue to prepare tools for the task, we will provide scripts that can convert back and forth from BIO to other formats (such as BIOES/BILOU).

SeqScore is being continuously updated, so you can always run `pip install -U seqscore` to get the latest.

## Schedule

* ~~February, 15~~: [Sample set](https://github.com/adobo-task/adobo-2021/tree/main/corpus), [Evaluation script](https://github.com/bltlab/seqscore) and [Annotation Guidelines](https://adobo-task.github.io/docs/guidelines.pdf) released.
* ~~March, 15~~: Training set released.
* ~~April,  5~~: Development set released.
* ~~May, 10~~: Test set released.
* ~~May,   17~~: Systems output submissions.
* ~~May,   20~~: Results posted and Test set with GS annotations released.
* ~~May,   31~~: Working notes paper submission.
* ~~June,  14~~: Notification of acceptance (peer-reviews).
* ~~June,  28~~: Camera ready paper submission.
* September, 21: ADoBo session at IberLEF 2021.

## Results

| Rank | Team         | Tag                 | Precision               | Recall                  | F1                          |
|------|--------------|---------------------|-------------------------|-------------------------|-----------------------------|
| 1    | marrouviere  | ALL<br>ENG<br>OTHER | 88.81<br>90.70<br>47.06 | 81.56<br>82.65<br>52.17 | **85.03**<br>86.49<br>49.48 |
| 2    | marrouviere  | ALL<br>ENG<br>OTHER | 89.40<br>90.98<br>45.45 | 66.30<br>67.55<br>32.61 | **76.14**<br>77.54<br>37.97 |
| 3    | marrouviere  | ALL<br>ENG<br>OTHER | 92.28<br>93.43<br>38.89 | 61.40<br>63.12<br>15.22 | **73.75**<br>75.34<br>21.88 |
| 4    | versae       | ALL<br>ENG<br>OTHER | 62.76<br>62.97<br>45.45 | 46.30<br>47.62<br>10.87 | **53.29**<br>54.23<br>17.54 |
| 5    | mgrafu       | ALL<br>ENG<br>OTHER | 65.15<br>65.31<br>50.00 | 37.82<br>38.90<br>08.69 | **47.86**<br>48.76<br>14.81 |
| 6    | Neakail      | ALL<br>ENG<br>OTHER | 75.27<br>75.43<br>60.00 | 27.47<br>28.25<br>6.52  | **40.25**<br>41.10<br>11.76 |
| 7    | Neakail      | ALL<br>ENG<br>OTHER | 76.29<br>76.48<br>60.00 | 25.29<br>25.99<br>6.52  | **37.99**<br>38.80<br>11.76 |
| 8    | Neakail      | ALL<br>ENG<br>OTHER | 76.44<br>76.64<br>60.00 | 24.75<br>25.42<br>6.52  | **37.39**<br>38.18<br>11.76 |

## How to participate?
ADoBo shared task is aimed at participants working in **code-mixed data** and those interested in the intersection of **neology, lexicography and NLP**. The dataset distribution and submissions will be managed via [CodaLab](https://competitions.codalab.org/competitions/28771). 

Participants (and anyone interested in the topic of borrowing detection) are welcome to join the Google group at [adobo-task[@]googlegroups.com](mailto:adobo-task@googlegroups.com)


## Organization Committee

* [Elena Álvarez-Mellado](https://lirondos.github.io/), USC Information Sciences Institute, USA.
* [Luis Espinosa-Anke](https://luis-espinosa-anke.jimdosite.com/), School of Computer Science and Informatics, Cardiff University, UK. 
* [Julio Gonzalo Arroyo](https://sites.google.com/view/nlp-uned/people/julio-gonzalo), Universidad Nacional de Educación a Distancia, Spain.
* [Constantine Lignos](https://lignos.org/), Brandeis University, USA.
* Jordi Porta-Zamorano, Centro de Estudios de la RAE, Spain.

## Contact

* Participants are encouraged to ask any questions through: [adobo-task[@]googlegroups.com](mailto:adobo-task@googlegroups.com)

* Elena Álvarez Mellado [ealvarezmellado[@]gmail.com](mailto:adobo-task@googlegroups.com)
