## Examples

Often, cross-linguistic data comes with examples, i.e. sentence-sized chunks of
text used to exemplify a statement about a language; e.g. showing
- usage of a particular lexeme in a language or
- existence of a particular construction.

Such examples have two basic properties: Text in the primary language and a
translation into a target language.

Often examples are glossed using
[Interlinear glossed text](http://en.wikipedia.org/wiki/Interlinear_gloss) 
according to the [Leipzig Glossing Rules](http://www.eva.mpg.de/lingua/resources/glossing-rules.php). In this case, the example is extended
with two properties: The aligned primary text and aligned glosses.

Thus, an `examples.csv` file or a table ẁith `"dc:type": "cldf:examples"` has
the following columns:
- `Primary_text`: required
- `Primary_text_aligned`: optional, words separated by tab `\t` (or a different separator if indicated by metadata)
- `Gloss_aligned`: optional, words separated by tab `\t` (or a different separator if indicated by metadata)
- `Translation`: required
- `Translation_language_ID`: optional. If missing, translations are interpreted as
  English text.

Note that words in gloss and aligned text may be further split into morphemes and clitics using `-` and `=` as separators according to the 
[Leipzig Glossing Rules](http://www.eva.mpg.de/lingua/resources/glossing-rules.php).
Thus, `-` and `=` must not be used for the separator property of the corresponding column.


### Editing examples

The CSV format for examples specified above is not particularly suited for editing
in particular not for interlinear glosses. The tool most often used for glossing
examples seems to be the *Field Linguist's Toolbox* (aka *Toolbox*) or successors
thereof. It should be noted, though, that conversion of CSV examples to and from
a format that can be read and edited by Toolbox is very simple. We basically have
to map the columns in the CSV specification to Toolbox markers. So, considering
a Toolbox example like
```
\ref xv1
\tx vyanten ente mwi abwilyep
\mb vyanten en=te mw=i abwilyep
\gl person $dem=$dem.med mw=i abwilyep
\ft this man is a sorcerer
```
(which uses markers as exported from tools like ELAN), we would map 
- `ID` to `\ref`
- `Primary_text` to `\tx`
- `Primary_text_aligned` to `\mb`
- `Gloss_aligned` to `\gl`
- `Translation` to `\ft`