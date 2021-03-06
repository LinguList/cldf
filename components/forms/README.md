## Forms

Forms, i.e. written denotations of the linguistic sign (cf. [GOLD's FormUnit](http://linguistics-ontology.org/gold/2010/FormUnit)), are stored in a
`FormTable` in CLDF datasets (typically `Wordlist`s).

Each form is stored as a separate row in this table, providing, at the least, the following columns:
 
- [ID](http://cldf.clld.org/v1.0/terms.rdf#id): A unique identifier for the row within the table.
- [Language_ID](http://cldf.clld.org/v1.0/terms.rdf#languageReference): A reference to a language (or variety) the form belongs to.
- [Parameter_ID](http://cldf.clld.org/v1.0/terms.rdf#parameterReference): A reference to the meaning denoted by the form.
- [Form](http://cldf.clld.org/v1.0/terms.rdf#form): The written expression of the form. If possible the transcription system used for the written form should be described in CLDF metadata (e.g. via adding a common property `dc:conformsTo` to the column description using concept URLs of the GOLD Ontology (such as [phonemicRep](http://linguistics-ontology.org/gold/2010/phonemicRep) or [phoneticRep](http://linguistics-ontology.org/gold/2010/phoneticRep)) as values).

Some analyses, e.g. alignments, require segmented lexical forms. If these can be supplied, they should be added in a [Segments](http://cldf.clld.org/v1.0/terms.rdf#segments) column, by default as space-separated strings.

The CLDF Ontology provides some more properties which may be supplied in corresponding columns of the `FormTable`:
- [Motivation_Structure](http://cldf.clld.org/v1.0/terms.rdf#motivationStructure)
- [Prosodic_Structure](http://cldf.clld.org/v1.0/terms.rdf#prosodicStructure)
- [Root](http://cldf.clld.org/v1.0/terms.rdf#root)
- [Stem](http://cldf.clld.org/v1.0/terms.rdf#stem)

A [Value](http://cldf.clld.org/v1.0/terms.rdf#value) column may be used to supply the raw value as it can be found in the source - if this is different
from `Form`. This is particularly useful for "retro-digitized" datasets, where
the CLDF dataset is already the result of data clean-up.

As with any CLDF component, 
- comments and references to sources can be added via
[Comment](http://cldf.clld.org/v1.0/terms.rdf#comment) and [Source](http://cldf.clld.org/v1.0/terms.rdf#source) columns respectively,
- additional data can be supplied in additional columns.


### Example

The [CLDF download](https://cdstar.shh.mpg.de/bitstreams/EAEA0-9C1A-66E2-D0B3-0/ids_dataset.cldf.zip) linked from
the download page of [The Intercontinental Dictionary Series](http://ids.clld.org) contains a `FormTable` starting with

```
ID,Language_ID,Parameter_ID,Form,Segments,Comment,Source,Contribution_ID
14-320-325-1,325,14-320,гьарза,,,,325
```

`Language_ID` and `Parameter_ID` provide references to rows in the `LanguageTable` and `ParameterTable`, respectively, in the same CLDF dataset.
The form is given in cyrillic transcription.
