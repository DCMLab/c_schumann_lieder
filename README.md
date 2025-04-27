![Version](https://img.shields.io/github/v/release/DCMLab/c_schumann_lieder?display_name=tag)
[![DOI](https://zenodo.org/badge/473148394.svg)](https://doi.org/10.5281/zenodo.14996952)
![GitHub repo size](https://img.shields.io/github/repo-size/DCMLab/c_schumann_lieder)
![License](https://img.shields.io/badge/license-CC%20BY--NC--SA%204.0-9cf)


This is a README file for a data repository originating from the [DCML corpus initiative](https://github.com/DCMLab/dcml_corpora)
and serves as welcome page for both 

* the GitHub repo [https://github.com/DCMLab/c_schumann_lieder](https://github.com/DCMLab/c_schumann_lieder) and the corresponding
* documentation page [https://dcmlab.github.io/c_schumann_lieder](https://dcmlab.github.io/c_schumann_lieder)

For information on how to obtain and use the dataset, please refer to [this documentation page](https://dcmlab.github.io/c_schumann_lieder/introduction).

When you use (parts of) this dataset in your work, please read and cite the accompanying data report:

_Hentschel, J., Rammos, Y., Neuwirth, M., & Rohrmeier, M. (2025). A corpus and a modular infrastructure for the 
empirical study of (an)notated music. Scientific Data, 12(1), 685. https://doi.org/10.1038/s41597-025-04976-z_

# Clara Schumann – Lieder (A corpus of annotated scores)

This corpus of annotated [MuseScore](https://musescore.org) files has been created within
the [DCML corpus initiative](https://github.com/DCMLab/dcml_corpora) and employs
the [DCML harmony annotation standard](https://github.com/DCMLab/standards). It consists of two song cycles by Clara
Schumann, op. 13 and op. 23, written about ten years apart. Op. 13, completed three years after the composer's marriage
to Robert Schumann, sets German Romantic poems by Heine, Geibel, and Rückert. Op. 23 was published with the title "6
Lieder aus Jucunde," drawing its text from the eponymous novel with poems by political radical Hermann Rollett, and was
composed during the flurry of activity that accompanied the composer's close friendship with Johannes Brahms. Both
cycles incorporate virtuosic piano accompaniments befitting their composer's status as a distinguished concert soloist.
The annotations in this corpus illustrate the equally rich details found in high-Romantic chromatic harmony and
counterpoint. 

## Getting the data

* download repository as a [ZIP file](https://github.com/DCMLab/c_schumann_lieder/archive/main.zip)
* download a [Frictionless Datapackage](https://specs.frictionlessdata.io/data-package/) that includes concatenations
  of the TSV files in the four folders (`measures`, `notes`, `chords`, and `harmonies`) and a JSON descriptor:
  * [c_schumann_lieder.zip](https://github.com/DCMLab/c_schumann_lieder/releases/latest/download/c_schumann_lieder.zip)
  * [c_schumann_lieder.datapackage.json](https://github.com/DCMLab/c_schumann_lieder/releases/latest/download/c_schumann_lieder.datapackage.json)
* clone the repo: `git clone https://github.com/DCMLab/c_schumann_lieder.git` 


## Data Formats

Each piece in this corpus is represented by five files with identical name prefixes, each in its own folder. 
For example, the first song, *Ich stand in dunklen Traumen*, of the first cycle, Op. 13 has the following files:

* `MS3/op13no1 Ich stand in dunklen Traumen.mscx`: Uncompressed MuseScore 3.6.2 file including the music and annotation labels.
* `notes/op13no1 Ich stand in dunklen Traumen.notes.tsv`: A table of all note heads contained in the score and their relevant features (not each of them represents an onset, some are tied together)
* `measures/op13no1 Ich stand in dunklen Traumen.measures.tsv`: A table with relevant information about the measures in the score.
* `chords/op13no1 Ich stand in dunklen Traumen.chords.tsv`: A table containing layer-wise unique onset positions with the musical markup (such as dynamics, articulation, lyrics, figured bass, etc.).
* `harmonies/op13no1 Ich stand in dunklen Traumen.harmonies.tsv`: A table of the included harmony labels (including cadences and phrases) with their positions in the score.

Each TSV file comes with its own JSON descriptor that describes the meanings and datatypes of the columns ("fields") it contains,
follows the [Frictionless specification](https://specs.frictionlessdata.io/tabular-data-resource/),
and can be used to validate and correctly load the described file. 

### Opening Scores

After navigating to your local copy, you can open the scores in the folder `MS3` with the free and open source score
editor [MuseScore](https://musescore.org). Please note that the scores have been edited, annotated and tested with
[MuseScore 3.6.2](https://github.com/musescore/MuseScore/releases/tag/v3.6.2). 
MuseScore 4 has since been released which renders them correctly but cannot store them back in the same format.

### Opening TSV files in a spreadsheet

Tab-separated value (TSV) files are like Comma-separated value (CSV) files and can be opened with most modern text
editors. However, for correctly displaying the columns, you might want to use a spreadsheet or an addon for your
favourite text editor. When you use a spreadsheet such as Excel, it might annoy you by interpreting fractions as
dates. This can be circumvented by using `Data --> From Text/CSV` or the free alternative
[LibreOffice Calc](https://www.libreoffice.org/download/download/). Other than that, TSV data can be loaded with
every modern programming language.

### Loading TSV files in Python

Since the TSV files contain null values, lists, fractions, and numbers that are to be treated as strings, you may want
to use this code to load any TSV files related to this repository (provided you're doing it in Python). After a quick
`pip install -U ms3` (requires Python 3.10 or later) you'll be able to load any TSV like this:

```python
import ms3

labels = ms3.load_tsv("harmonies/op13no1 Ich stand in dunklen Traumen.harmonies.tsv")
notes = ms3.load_tsv("notes/op13no1 Ich stand in dunklen Traumen.notes.tsv")
```


## Version history

See the [GitHub releases](https://github.com/DCMLab/c_schumann_lieder/releases).

## Questions, Suggestions, Corrections, Bug Reports

Please [create an issue](https://github.com/DCMLab/c_schumann_lieder/issues) and/or feel free to fork and submit pull requests.

## Cite as

> Hentschel, J., Rammos, Y., Neuwirth, M., & Rohrmeier, M. (2025). A corpus and a modular infrastructure for the empirical study of (an)notated music. Scientific Data, 12(1), 685. https://doi.org/10.1038/s41597-025-04976-z

## License

Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License ([CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/)).

![cc-by-nc-sa-image](https://licensebuttons.net/l/by-nc-sa/4.0/88x31.png)


## Scores

These piano scores were downloaded from the
wonderful [OpenScore Lieder](https://github.com/OpenScore/Lieder/tree/main/scores/Schumann%2C_Clara) project and
minimally reformatted for annotation use. They correspond well to the widely-available first editions from Breitkopf und
Härtel.

## File naming convention

```regex
op(?<op>\d{2})
no(?<no>\d)\s
(?<title>.+)
```

## Overview
|               file_name               |measures|labels|standard| annotators |reviewers|
|---------------------------------------|-------:|-----:|--------|------------|---------|
|op13no1 Ich stand in dunklen Traumen   |      37|   103|2.3.0   |Adrian Nagel|AB       |
|op13no2 Sie liebten sich beide         |      34|   108|2.3.0   |Adrian Nagel|AB       |
|op13no3 Liebeszauber                   |      54|   155|2.3.0   |Adrian Nagel|AB       |
|op13no4 Der Mond kommt still gegangen  |      33|   120|2.3.0   |Adrian Nagel|AB       |
|op13no5 Ich hab in deinem Auge         |      33|   109|2.3.0   |Adrian Nagel|AB       |
|op13no6 Die stille Lotosblume          |      47|   118|2.3.0   |Adrian Nagel|AB       |
|op23no1 Was weinst du Blumlein         |      68|   139|2.3.0   |Adrian Nagel|AB       |
|op23no2 An einem lichten Morgen        |      38|    94|2.3.0   |Adrian Nagel|AB       |
|op23no3 Geheimes Flustern hier und dort|      50|    74|2.3.0   |Adrian Nagel|AB       |
|op23no4 Auf einem grunen Hugel         |      30|    94|2.3.0   |Adrian Nagel|AB       |
|op23no5 Das ist ein Tag der klingen mag|      45|   122|2.3.0   |Adrian Nagel|AB       |
|op23no6 O Lust o Lust                  |      40|    90|2.3.0   |Adrian Nagel|AB       |


*Overview table automatically updated using [ms3](https://ms3.readthedocs.io/).*
