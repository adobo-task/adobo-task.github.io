# What is ADoBo?
ADoBo is the shared task on **automatic detection of borrowings**. For the first edition of ADoBo, we propose a shared task on detecting direct, unadapted, emerging borrowings in the Spanish press, i.e. detecting lexical borrowings that appear in the Spanish press and that have recently been imported into the Spanish language (words like _running_, _smartwatch_, _influencer_ or _cliffhanger_). 

The task will run from February 2021 to June 2021 and is part of [IberLEF 2021](https://sites.google.com/view/iberlef2021/), which will take place in September 2021 in Spain.

# What is a lexical borrowing?
Lexical borrowing is the process of importing words from one language into another language. Lexical borrowing is a phenomenon that affects all languages and is in fact a productive mechanism of word formation. During the last decades, English in particular has produced numerous lexical borrowings (often called _anglicisms_) in many European languages, especially in the press. It has been estimated that a reader of French newspapers [encounters a new lexical borrowing every 1,000 words](https://www.degruyter.com/view/journals/ling/48/6/article-p1343.xml), English borrowings outnumbering all other borrowings combined. In Chilean newspapers, lexical borrowings account for approximately 30% of neologisms, [80% of those corresponding to English borrowings](http://www.scielo.org.co/scielo.php?script=sci_arttext&pid=S0123-46412014000100005). In European Spanish, it has been estimated that [anglicisms could account for 2% of the vocabulary used in Spanish newspaper El País in 1991](https://rua.ua.es/dspace/bitstream/10045/18872/1/Felix_Rodriguez_Anglicisms.pdf), a number that is likely to be higher today. 

As a result, the presence of English borrowings into Spanish has attracted lots of attention, both in Linguistics studies and among the general public. 

# Why is lexical borrowing detection interesting?
The task of automatically extracting unadapted lexical borrowings from text is relevant both for lexicographic purposes and for NLP downstream tasks. Borrowing detection has previously been used as a preprocessing step for [parsing](https://homepages.inf.ed.ac.uk/balex/publications/thesis.pdf), [text-to-speech synthesis](https://www.csl.uni-bremen.de/cms/images/documents/publications/SLTU2014-LeidigSchlippe_AnglicismDetection.pdf) and [machine translation](https://www.cs.cmu.edu/~ytsvetko/papers/loanwords-jair.pdf). 

In the last years, several projects have approached the problem of extracting lexical borrowings in different European languages such, as [German](https://www.aclweb.org/anthology/P12-2027/), [Italian](https://brill.com/view/book/edcoll/9789401204347/B9789401204347-s020.xml), [French](https://www.degruyter.com/view/j/ling.2010.48.issue-6/ling.2010.043/ling.2010.043.xml), [Finnish](https://www.aclweb.org/anthology/W12-2705/) or [Norwegian](https://benjamins.com/catalog/z.174.09and), with a particular focus on anglicism extraction. Lately, work on anglicism detection in Spanish language has also been done for [Argentinian Spanish](https://repositories.lib.utexas.edu/handle/2152/63064) and [European Spanish](http://bir.brandeis.edu/handle/10192/37532). 


# What makes borrowing detection challenging?
The task of extracting emergent lexical borrowings is a more challenging undertaking than it might appear to be at first. To begin with, lexical borrowings can be either single or multitoken expressions (e.g., _prime time_, _tie break_ or _machine learning_). Second, plain dictionary lookup can be an unreliable source for borrowing detection: after all, a term like _social media_ is a borrowing, even when the two tokens that form the term happen to be Spanish words that appear in Spanish dictionaries. 

Finally, linguistic adaptation is a diachronic proccess and, as a result, what constitutes an unadapted borrowing is not clear-cut. For example, words like _bar_ or _club_ were unadapted lexical borrowings in Spanish at some point in the past, but have been around for so long in the Spanish language that the process of phonological and morphological adaptation is now complete and they cannot be considered unadapted borrowings anymore. On the other hand, _realia_ words, that is, culture-specific elements whose name entered via the language of origin decades ago (like _jazz_ or _whisky_) cannot be considered emergent anymore, even when their orthography has not been adapted into the Spanish spelling system. 

# ADoBo shared task
A corpus of Spanish newswire will be distributed among participants. The articles will be annotated with direct, unadapted, emerging lexical borrowings, i.e. lexical borrowings that have recently been imported into Spanish language (such as _look_, _hype_, _youtuber_ or _lawfare_). Borrowings will be annotated with BIO labels with two possible categories: ``ENG`` for English borrowings and ``OTHER`` for lexical borrowings from other languages (non lexical borrowings will have the tag ``O``). Only unadapted lexical borrowings will be considered. This means that borrowings that have already gone through orthographical or morphological adaption (such _fútbol_ or _hackear_) will not be labeled as borrowings. 

Participants will be provided with annotated versions of the training and development set, and an unannotated test set. Participants are expected to submit the annotated test set produced by their system.  

Submissions will be evaluated using the standard precision, recall and F1 over spans:
* Precision: The percentage of borrowings in the system’s output that are correctly recognized and classified.
* Recall: The percentage of borrowings in the test set that were correctly recognized and classified.
* F1-measure: The harmonic mean of Precision and Recall.

F1-measure will be used as the oﬀicial evaluation score, and will be used for the final ranking of the participating teams. 

It should be noted that the evaluation for the final ranking will be done exclusively at the *span level*. This means that only full matches will be considered, and no credit will be given to partial matches, i.e. given the multitoken borrowing _late night_, the entire phrase would have to be correctly labeled in order to count as a true positive. 


# How to participate?
ADoBo shared task is aimed at participants working in code-mixed data and those interested in the intersection of neology, lexicography and NLP. The dataset distribution and submissions will be managed via CodaLab. Participants (and anyone interested in the topic of borrowing detection) are welcome to join the Google group at [adobo-task[@]googlegroups.com](mailto:adobo-task@googlegroups.com)


# Schedule

* February, 15: Sample set, Evaluation script and Annotation Guidelines released.
* March, 15: Training set released.
* April,  5: Development set released.
* April, 26: Test set released.
* May,   17: Systems output submissions.
* May,   21: Results posted and Test set with GS annotations released.
* May,   31: Working notes paper submission.
* June,  14: Notification of acceptance (peer-reviews).
* June,  28: Camera ready paper submission.
* September: IberLEF 2021 Workshop.

# Organization Committee

* [Elena Álvarez-Mellado](https://lirondos.github.io/), USC Information Sciences Institute, US.
* [Luis Espinosa-Anke](https://luis-espinosa-anke.jimdosite.com/), School of Computer Science and Informatics, Cardiff University, UK. 
* [Julio Gonzalo Arroyo](https://sites.google.com/view/nlp-uned/people/julio-gonzalo), Universidad Nacional de Educación a Distancia, Spain.
* [Constantine Lignos](https://lignos.org/), Brandeis University, US.
* Jordi Porta-Zamorano, Centro de Estudios de la RAE, Spain.

# Contact

* Participants are encouraged to ask any questions through: [adobo-task[@]googlegroups.com](mailto:adobo-task@googlegroups.com)

* Elena Álvarez Mellado [ealvarezmellado@gmail.com](mailto:adobo-task@googlegroups.com)
