# What is ADoBo?
ADoBo is the shared task on automatic detection of borrowings. For the first edition of ADoBo, we propose a shared task on detecting direct, unadapted, emerging borrowings in the Spanish press, i.e. detecting lexical borrowings that appear in the Spanish press and that have recently been imported into the Spanish language (words like _running_, _smartwatch_, _influencer_, _holding_). 

The task will run from February 2021 to June 2021 and is be part of (IberLEF 2021)[https://sites.google.com/view/iberlef2021/], which will take place in September 2021 in Spain.

# What is a lexical borrowing?
Lexical borrowing is the process of importing words from one language into another language. Lexical borrowing is a phenomenon that affects all languages and is in fact a productive mechanism of word formation. During the last decades, English in particular has produced numerous lexical borrowings (often called _anglicisms_) in many European languages, especially in the press. \cite{chesley_paula_predicting_2010} estimated that a reader of French newspapers encounters a new lexical borrowing every 1,000 words, English borrowings outnumbering all other borrowings combined \citep{chesley2010lexical}. In Chilean newspapers, lexical borrowings account for approximately 30\% of neologisms, 80\% of those corresponding to English loanwords \citep{gerding2014anglicism}. In European Spanish, \cite{gorlach_felix} estimated that anglicisms could account for 2\% of the vocabulary used in Spanish newspaper El País in 1991, a number that is likely to be higher today. As a result, the presence of English borrowings into Spanish has attracted lots of attention, both in Linguistics studies and among the general public. 

# Why is lexical borrowing detection interesting?
The task of automatically extracting unadapted lexical borrowings from text is relevant both for lexicographic purposes and for NLP downstream tasks. Borrowing detection has previously been used as a preprocessing step in parsing \citep{alex2008automatic}, text-to-speech synthesis \citep{leidig2014automatic} and machine translation \citep{tsvetkov2016cross}. In the last years, several projects have approached the problem of extracting lexical borrowings in different European languages such, as German \citep{alex-2008-comparing,garley-hockenmaier-2012-beefmoves,leidig2014automatic}, Italian \citep{furiassi2007retrieval}, French \citep{alex2008automatic,chesley2010lexical}, Finnish \citep{mansikkaniemi2012unsupervised} or Norwegian \citep{andersen2012semi,losnegaard2012data}, with a particular focus on anglicism extraction. 


# What makes borrowing detection challenging
The task of extracting emergent lexical borrowings is a more challenging undertaking than it might appear to be at first. To begin with, lexical borrowings can be either single or multitoken expressions (e.g., _prime time_, _tie break_ or _machine learning_). Finally, linguistic adaptation is a diachronic proccess and, as a result, what constitutes an unadapted borrowing is not clear-cut. For example, words like _bar_ or _club_ were unadapted lexical borrowings in Spanish at some point in the past, but have been around for so long in the Spanish language that the process of phonological and morphological adaptation is now complete and they cannot be considered unadapted borrowings anymore. On the other hand, _realia_ words, that is, culture-specific elements whose name entered via the language of origin decades ago (like _jazz_ or _whisky_) cannot be considered emergent anymore, even when their orthography has not been adapted into the Spanish spelling system. 

Additionally, plain dictionary lookup can be an unreliable method for borrowing detection: after all, a term like _social media_ is a borrowing, even when the two tokens that form the term happen to be Spanish words that appear in Spanish dictionaries. 



\subsection{Target community and scope}
With ADoBo, we propose a shared task to detect unadapted emergent lexical borrowings in an anglicism-rich corpus of Spanish newswire. This is a task that can appeal to participants working in code-mixed data and those interested in the intersection of neology, lexicography and NLP.




\section{Corpus} 
A corpus of Spanish newswire will be distributed among participants. The articles will be annotated with direct, unadapted, emerging lexical borrowings, i.e. lexical borrowings that have recently been imported into Spanish language (such as _look_, _hype_, _prime time_ or _lawfare_). Borrowings will be annotated with BIO labels with two possible categories: ENG for English borrowings and OTHER for lexical borrowings from other languages (non lexical borrowings will have the tag O). Only unadapted lexical borrowings will be considered. This means that borrowings that have already gone through orthographical or morphological adaption (such _fútbol_ or _hackear_) will not be labeled as borrowings. 


\section{Evaluation} 

The evaluation metrics used in this task will be the standard precision, recall and F1 over spans:
\begin{itemize}
    \item Precision: The percentage of borrowings in the system’s output that are correctly recognized and classified.
    \item Recall: The percentage of borrowings in the test set that were correctly recognized and classified.
    \item F1-measure: The harmonic mean of Precision and Recall.
\end{itemize}

F1-measure will be used as the oﬀicial evaluation score, and will be used for the final ranking of the participating teams. 

It should be noted that the evaluation for the final ranking will be done exclusively at the span level. This means that only full matches will be considered, and no credit will be given to partial matches, i.e. given the multitoken borrowing _late night_, the entire phrase would have to be correctly labeled in order to count as a true positive. This makes the evaluation more rigorous, as it avoids the overstating that can sometimes result from token level evaluation (for instance, a model that would only detect English function words could detect _on_ and _the_ in _on the rocks_ or _by_ in _stand by_ and still get a generous result on a token-level evaluation). Although the final ranking will be based on full matches at the span level, additional evaluation metrics (such as partial matching and untyped span evaluation) may be reported to gain a better understanding of how the different models perform. 

# Schedule

* February, 15: Sample set, Evaluation script and Annotation Guidelines released.
* March, 15: Training set released.
* April,  5: Development set released.
* April, 26: Test set released (includes background set).
* May,   17: Systems output submissions.
* May,   21: Results posted and Test set with GS annotations released.
* May,   31: Working notes paper submission.
* June,  14: Notification of acceptance (peer-reviews).
* June,  28: Camera ready paper submission.
* September: IberLEF 2021 Workshop.

# Organization Committee

* Elena Álvarez-Mellado, USC Information Sciences Institute, US.
* Luis Espinosa-Anke, School of Computer Science and Informatics, Cardiff University, UK. 
* Julio Gonzalo Arroyo, Universidad Nacional de Educación a Distancia, Spain.
* Constantine Lignos, Brandeis University, US.
* Jordi Porta-Zamorano, Centro de Estudios de la RAE, Spain.

#Contact person

Elena Álvarez Mellado (ealvarezmellado@gmail.com)
