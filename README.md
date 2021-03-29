# Chunking Historical German

This repository contains the manually annotated data sets and additional material for the paper:

Katrin Ortmann (to appear). Chunking Historical German. Reykjavik, Iceland (online).

## Gold data

The manually annotated data sets can be found in the `data` folder. Included are:

- 547 sentences from five written modern registers from [Ortmann et al. (2019)](https://github.com/rubcompling/konvens2019),
- 342 sentences from the HIPKON corpus [(Coniglio et al., 2014)](https://doi.org/10.34644/laudatio-dev-yiTKCnMB7CArCQ9CxLhJ)
- and 606 sentences from the DTA [(German Text Archive; BBAW, 2019)](http://www.deutschestextarchiv.de/).

The data sets were taken from a previous study on topological fields [(Ortmann, 2020)](https://www.aclweb.org/anthology/2020.latechclfl-1.2.pdf) and enriched with chunks as well as additional corrections of POS tags and sentence boundaries. More information on these data sets including a mapping of HIPKON POS tags to STTS can be found [here](https://github.com/rubcompling/latech2020).

The data is available in CoNLL2000 format (cf. [Sang & Buchholz, 2000](https://www.aclweb.org/anthology/W00-0726.pdf)) and contains word forms, [STTS POS tags](http://www.sfs.uni-tuebingen.de/resources/stts-1999.pdf), and BIO chunks, separated by spaces.

The following chunk types are included:

- `NC` (noun chunk)
- `PC` (prepositional chunk)
- `ADVC` (adverb chunk)
- `AC` (adjective chunk)
- `sNC` (stranded noun chunk)
- `sPC` (stranded prepositional chunk)

## Additional material

### Mercurius POS to STTS mapping

The following mapping rules are used to derive STTS tags (Schiller et al., 1999) from the POS tagset of the [Mercurius](https://doi.org/10.34644/laudatio-dev-VyQiCnMB7CArCQ9CjF3O) corpus (Demske, 2005). Tags not listed here remain unchanged.

 **POS** | **STTS** 
---------|-------------
$! | $.
$: | $.	
$; | $.
$? | $.
-- | XY
KOMPE | POS of following token
NNE | NN
PROAV | PAV
UNKNOWN | XY
VVPG | ADJD

### ReF.UP POS to STTS mapping

The following mapping rules are used to derive STTS tags (Schiller et al., 1999) from the POS tagset of the ReF.UP corpus, a subcorpus of the [Reference Corpus of Early New High German](https://www.linguistics.rub.de/ref) (Wegera et al., 2021). A documentation (in German) can be found [here](https://www.uni-potsdam.de/fileadmin/projects/guvdds/Dateien/Wortartinformation.pdf).

 **POS** | **STTS** 
---------|-------------
-- | XY
$! | $.
$( | $(
$, | $,
$. | $.
$: | $.
$; | $.
$? | $.
$MK | $,
$MSBI | $.
$QL | $(
$QR | $(
ADJA | ADJA
ADJD | ADJD
ADJN | ADJD
ADJS | ADJA
ADJV | ADJD
ADV	 | ADV
APPO | APPO
APPR | APPR
APPRDARTB | APPRART
APZR | APZR
AVD | ADV
AVNEG | ADV
AVREL | ADV
AVW | PWAV
CARD | CARD
DARTB | ART
DARTU | ART
DDEM | PDAT
DINDEF | PIAT
DPOS | PPOSAT
DW | PWAT
FM | FM
ITJ | ITJ
KOKOM | KOKOM
KON | KON
KOUI | KOUI
KOUS | KOUS
NA | NN
NE | NE
PAVAP | ADV
PAVD | ADV
PAVDAP | PAV
PAVREL | ADV
PAVRELAP | PAV
PAVW | PWAV
PAVWAP | PWAV
PDEM | PDS
PINDEF | PIS
PPER | PPER
PPOS | PPOSS
PRELAT | PRELAT
PRELS | PRELS
PRF | PRF
PTKA | PTKA
PTKANT | PTKANT
PTKNEG | PTKNEG
PTKREL | ADV
PTKVZ | PTKVZ
PTKZU | PTKZU
PW | PWS
PWAV | PWAV
SPELL | XY
TRUNC | TRUNC
VAFIN | VAFIN
VAIMP | VAIMP
VAINF | VAINF
VAINFS | VAINF
VAPP | VAPP
VAPPA | ADJA
VAPPD | ADJD
VAPPN | VAPP
VAPSA | ADJA
VAPSD | ADJD
VAPSN | VAPP
VAPSS | NN
VMFIN | VMFIN
VMIMP | VMIMP
VMINF | VMINF
VMINFS | NN
VMPP | VMPP
VVFIN | VVFIN
VVIMP | VVIMP
VVINF | VVINF
VVINFS | NN
VVIZU | VVIZU
VVPP | VVPP
VVPPA | ADJA
VVPPD | ADJD
VVPPN | VVPP
VVPPS | NN
VVPS | VVPP
VVPSA | ADJA
VVPSD | ADJD
VVPSN | VVPP
VVPSS | NN


### RegExp Rules

The following rules are used for chunk identification with the [RegExp chunker](https://www.nltk.org/api/nltk.chunk.html):

```
PC:
{<KOKOM>*<APPR><(ART|PPOSAT|PDAT|PIAT|PWAT|CARD|ADJA|ADJD|ADV|PTKNEG|$,|$\(|KON|TRUNC)>*<(NN|NE)>+<APZR>*}
{<KOKOM>*<APPRART><(CARD|ADJA|ADJD|ADV|PTKNEG|$,|$\(|KON|TRUNC)>*<(NN|NE)>+<APZR>*}
{<KOKOM>*<(ART|PPOSAT|PDAT|PIAT|PWAT|CARD|ADJA|TRUNC)><(ART|PPOSAT|PDAT|PIAT|PWAT|CARD|ADJA|ADJD|ADV|PTKNEG|$,|$\(|KON|TRUNC)>*<(NN|NE)>+<APPO>+}
{<KOKOM>*<(ART|PPOSAT|PDAT|PIAT|PWAT|CARD|ADJA|TRUNC)>*<(NN|NE)>+<APPO>+}
{<KOKOM>*<APPR><ART><(PIS|PPOSS)><APZR>*}
{<KOKOM>*<ART><(PIS|PPOSS)><APPO>}
{<KOKOM>*<(APPR|APPRART)><(PIS|PDS|PWS|PPER|PPOSS|PRELS|PRF)><APZR>*}
{<KOKOM>*<(PIS|PDS|PWS|PPER|PPOSS|PRELS|PRF)><APPO>}
{<KOKOM>*<APPR>*<PAV>}
NC:
{<KOKOM>*<(ART|PPOSAT|PDAT|PIAT|PWAT|CARD|ADJA|TRUNC)><(ART|PPOSAT|PDAT|PIAT|PWAT|CARD|ADJA|ADJD|ADV|PTKNEG|$,|$\(|KON|TRUNC)>*<(NN|NE)>+}
{<KOKOM>*<(ART|PPOSAT|PDAT|PIAT|PWAT|CARD|ADJA|TRUNC)>*<(NN|NE)>+}
{<KOKOM>*<ART><(PIS|PPOSS)>}
{<KOKOM>*<(PIS|PDS|PWS|PPER|PPOSS|PRELS|PRF)>}
AC:
{<KOKOM>*<(ADJA|ADV|PTKNEG|PTKA)>*<ADJD>+}
ADVC:
{<KOKOM>*<(ADV|PTKNEG)>+}
NC:
{<KOKOM>*<CARD>+}
sPC:
{<KOKOM>*<(APPR|APPRART)><(ART|PPOSAT|PDAT|PIAT|PWAT|ADJA)>*}
sNC:
{<KOKOM>*<(ART|PPOSAT|PDAT|PIAT|PWAT|ADJA)>}
```        

## References

BBAW. 2019. Deutsches Textarchiv. Grundlage für ein Referenzkorpus der neuhochdeutschen Sprache. Berlin-Brandenburgische Akademie der Wissenschaften; http://www.deutschestextarchiv.de/.

Marco Coniglio, Karin Donhauser, and Eva Schlachter. 2014. HIPKON: Historisches Predigtenkorpus zum Nachfeld (Version 1.0). Humboldt-Universität zu Berlin. SFB 632 Teilprojekt B4.

Ulrike Demske. 2005. Mercurius-Baumbank (Version 1.1). Universität Potsdam. [LAUDATIO access](https://doi.org/10.34644/laudatio-dev-VyQiCnMB7CArCQ9CjF3O)

Katrin Ortmann, Adam Roussel, and Stefanie Dipper. 2019. Evaluating Off-the-Shelf NLP Tools for German. In *Proceedings of the Conference on Natural Language Processing (KONVENS)*, pages 212–222.

Katrin Ortmann. 2020. Automatic Topological Field Identification in (Historical) German Texts. In *Proceedings of the The 4th Joint SIGHUM Workshop on Computational Linguistics for Cultural Heritage, Social Sciences, Humanities and Literature (LaTeCH-CLfL)*, pages 10-18.

Anne Schiller, Simone Teufel, Christine Stöckert, and Christine Thielen. 1999. *Guidelines für das Tagging deutscher Textcorpora mit STTS (Kleines und großes Tagset)*. Retrieved from http://www.sfs.uni-tuebingen.de/resources/stts-1999.pdf.

Klaus-Peter Wegera, Hans-Joachim Solms, UlrikeDemske, and Stefanie Dipper. 2021. Referenzkorpus Frühneuhochdeutsch (Version 1.0). https://www.linguistics.rub.de/ref

