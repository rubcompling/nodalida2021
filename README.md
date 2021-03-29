# Chunking Historical German

This repository contains the manually annotated data sets and additional material for the paper:

Katrin Ortmann (to appear). Chunking Historical German. Reykjavik, Iceland (online).

## Gold data

The manually annotated data sets can be found in the `data` folder. Included are:

- 547 sentences from five written modern registers from [Ortmann et al. (2019)](https://github.com/rubcompling/konvens2019),
- 342 sentences from the HIPKON corpus [(Coniglio et al., 2014)](https://doi.org/10.34644/laudatio-dev-yiTKCnMB7CArCQ9CxLhJ)
- and 606 sentences from the DTA [(German Text Archive; BBAW, 2019)](http://www.deutschestextarchiv.de/).

The data sets were taken from a previous study on topological fields [(Ortmann, 2020)](https://www.aclweb.org/anthology/2020.latechclfl-1.2.pdf) and enriched with chunks as well as additional corrections of POS tags and sentence boundaries. More information on these data sets including a mapping of HIPKON POS tags to STTS can be found [here](https://github.com/rubcompling/latech2020).

The data is available in CoNLL2000 format (cf. [Sang & Buchholz, 2000](https://www.aclweb.org/anthology/W00-0726.pdf)) and contains word forms, STTS POS tags (Schiller et al., 1999), and BIO chunks, separated by spaces.

## Additional material

### Mercurius POS to STTS mapping

### ReF.UP POS to STTS mapping

### RegExp Rules

## References

BBAW. 2019. Deutsches Textarchiv. Grundlage für ein Referenzkorpus der neuhochdeutschen Sprache. Berlin-Brandenburgische Akademie der Wissenschaften; http://www.deutschestextarchiv.de/.

Marco Coniglio, Karin Donhauser, and Eva Schlachter. 2014. HIPKON: Historisches Predigtenkorpus zum Nachfeld (Version 1.0). Humboldt-Universität zu Berlin. SFB 632 Teilprojekt B4.

Katrin Ortmann, Adam Roussel, and Stefanie Dipper. 2019. Evaluating Off-the-Shelf NLP Tools for German. In *Proceedings of the Conference on Natural Language Processing (KONVENS)*, pages 212–222.

Katrin Ortmann. 2020. Automatic Topological Field Identification in (Historical) German Texts. In *Proceedings of the The 4th Joint SIGHUM Workshop on Computational Linguistics for Cultural Heritage, Social Sciences, Humanities and Literature (LaTeCH-CLfL)*, pages 10-18.

Anne Schiller, Simone Teufel, Christine Stöckert, and Christine Thielen. 1999. *Guidelines für das Tagging deutscher Textcorpora mit STTS (Kleines und großes Tagset)*. Retrieved from http://www.sfs.uni-tuebingen.de/resources/stts-1999.pdf.


