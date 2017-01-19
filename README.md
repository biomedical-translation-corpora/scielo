# Scielo dataset

This dataset contains documents retireved from the [Scielo](http://scielo.org/) database. 
It includes [parallel documents](link) for three language pairs, as well as [monolingual corpora](http://github.com/biomedical-translation-corpora/scielo/tree/master/monolingual) for each of the four languages. 
The documents can be composed of either a title, the abstract or both of them, depending on their availability in the database.
We split the dataset in "Biological Sciences" and "Health Sciences" according to the category to which the corresponding journal is indexed in Scielo.

- English-French and French-English
- English-Spanish and Spanish-English
- English-Portuguese and Portuguese-English

The Scielo dataset is available in the [BioC XML format](http://bioc.sourceforge.net/), for which readers and writers are available for many programming languages, as well as various natural language processing tools for biomedicine. There are specific values for the attribute "key" of the XML tag "infon" to identify the language of each document, the section (title or abstract) and the number of the sentence, as illustrated in the example below:

```
<document>
<id>S0034-77441998000200003</id>
<passage>
<infon key="language">EN</infon>
<infon key="section">abstract</infon>
<sentence>
<infon key="sentnum">0</infon>
<text>The gastrointestinal activity of an aqueous extract of the dry wood of Quassia amara was investigated using animal models. </text>
</sentence>
<sentence>
<infon key="sentnum">1</infon><offset>-1</offset><text> Oral administration of the extract to mice produces an increase of gastrointestinal transit at doses of 
500 and 1000 mg/kg. The antiulcerogenic activity was measured inducing ulcers on Sprague-Dowly rats with indomethacin or ethanol and by the induction of stress.</text>
</sentence>
<sentence>
<infon key="sentnum">2</infon>
<text> The experimental group was treated orally with the extract, using doses of 250, 500 and 1000 mg/kg before inducing the ulcers.</text>
</sentence>
...
</passage>
</document>
```

We aligned the documents from the Scielo database using the [GMA tool](http://nlp.cs.nyu.edu/GMA/). The files derived from this alignment  include the following files for each section of the document (title and abstract/text):

- *.crp: aligned sentences
- *.simr: GMA's word alignment file
- *.align: GMA's sentence alignment file
- *.txt.axis: GMA's axis file, one per language
- *.txt: plain text file, one per language

