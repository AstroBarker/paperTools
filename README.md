# Paper Tools for LaTeX

This is a collection of tools for writing papers, etc. using LaTeX. It is 
principally geared toward submissions to ApJ and friends. The includes a 
large bibTex database that can be continually updated and expanded, `mainDB.bib`.

Occasionally formatted with [bibtex-tidy](https://github.com/FlamingTempura/bibtex-tidy).

## Using BibTeX database and bibtool

Generally, it's expected that the `mainDB.bib` will be used in conjunction 
with the very handy [bibtool](https://www.ctan.org/tex-archive/biblio/bibtex/utils/bibtool/?lang=en). 
Bibtool can be installed easily on Macs using [Homebrew](https://brew.sh). 
Once you have bibtool installed somewhere in your path, you need to set the 
environment variable `PTOOLSDIR` so that it points at this repo so that 
the `mainDB.bib` can be found. With bash, you can set this as follows:

```sh
export PTOOLSDIR=/path/to/paperTools
```

After that's all set, you can build a custom bib file for your current 
document using the included Makefile by executing `make bib`. This will 
use bibtool to read your aux file and then extract the needed references 
from `mainDB.bib` into a `ms.bib` in the document directory.

The `mainDB.bib` file is sometimes managed with [jabref](https://www.jabref.org/) 
and specifies the reference key format as `firstauthor:year`, i.e., `barker:2022`. 
Duplicate keys are appended by letters, i.e., `barker:2022a` would be the _second_ 
paper in 2022 with a first author last name of Barker. Don't mess this up.

