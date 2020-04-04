---
title: Computing brain connectivity using portable devices - Master's Thesis
date: 2018-04-04 18:40:41
tags: neuroscience
---

The topic of my master's thesis was neuroscience. I studied how to use low cost portable electroenchephalographs for advanced  connectivity studies. [Here](https://github.com/mathigatti/EmotivExperiments) is the code for the experiments I coded and [here](https://github.com/mathigatti/EmotivClassifier) the classifiers I used in my thesis to infer different states based on neural connectivity. These things together with the great work of Marcos Pietto and his team ended up in the publications of [this](https://www.ncbi.nlm.nih.gov/pubmed/30475814) paper.

![](emotiv.jpg)

## Abstract

This is the abstract of my thesis, you can read the full version [here](http://dc.sigedep.exactas.uba.ar/media/academic/grade/thesis/Tesis_Mathias_Gatti.pdf) (It's in Spanish).
```
Electroencephalography (EEG) studies have shown to be a fundamental tool in the understanding of human cognitive processes and as a complementary method for clinical diagnosis. EEG recordings are usually restricted to the lab’s environment, which is an important limitation to the study of populations that are difficult to move to the lab or that this environment causes an effect by itself (such as little naturalness or stress). Recently, new EEG equipment at a significant lower cost and greater portability emerged mainly for gaming. However, the use of this equipment could open the possibility in the long term of application of different clinical and research protocols in more ecologically valid environments.

It is possible to build networks from the EEG recordings by looking at the similarity between the different electrodes, but there are many ways to define this similarity. In this thesis, we aimed to compare the resulting network by applying different measures, in terms of their robustness and their ability to predict different attributes of the subjects.

Thus, in the first place, we developed an experimentation environment that allowed both data collection in the lab and massive data collection in the schools. Two data sets were analyzed, the first including the low-cost EEG and the high-resolution EEG in adults, and the second with only the low-cost EEG in preschool children at the schools.

The results showed that some similarity measures are robust enough to analyze brain activity at the level of networks using the Emotiv system. In particular, we performed different experiments using the adult dataset, of which the PLV (Phase Locking value) and the correlation measures (both Spearman and Pearson) consistently gave the best results. Then, the preschool children dataset were analyzed using these measures and some individual variables, such as sleep level, sex and the distinction between open and closed eyes, were successfully predicted (AUC>0.67). As a final step, the code was released online, allowing anyone to replicate the data collection and connectivity analysis with the Emotiv system.

This thesis paves the way for the massive recording of brain activity with different paradigms and, in particular, the study of changes in brain connectivity throughout development, in more ecologically valid environments.
```