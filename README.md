# detag

## Introduction

The `detag` script is a short utility I wrote as an exercise in shell
programming with PHP.  It strips HTML tags and entities from file arguments
(or from `STDIN` if no arguments are provided).  The resulting text is then
written to the standard output.

## Function

The following selection of HTML is from the Wikipedia page on the great
author Herman Melville:

```html
<p><b>Herman Melville</b><sup id="cite_ref-1" class="reference"><a
href="#cite_note-1">[a]</a></sup> (August 1, 1819&nbsp;– September 28, 1891)
was an American <a href="/wiki/Novelist" title="Novelist">novelist</a>, short
story writer, and <a href="/wiki/Poet" title="Poet">poet</a> of the <a
href="/wiki/American_Renaissance_(literature)" title="American Renaissance
(literature)">American Renaissance</a> period. His best known works include ...</p>
```

If this file is saved to `melville.html`, one can simply run `detag
melville.html` or `cat melville.html | detag` to print the contents of the
file with all tags removed and all entities decoded.

An even more useful command is `detag melville.html | fmt`, which produces
the following output:

> Herman Melville[a] (August 1, 1819 – September 28, 1891) was
> an American novelist, short story writer, and poet of the American
> Renaissance period. His best known works include ...

Multiple file arguments can be specified, and the output will be printed as
one blob of text.

## Use

Admittedly, this tool is not very sophisticated.  It's really just a nifty
toy.  You might use it in a simple shell script or as a filter for some
nasty lines of markup in your favorite text editor.
