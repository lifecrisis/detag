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
was an American <a href="/wiki/Novelist" title="Novelist">novelist</a>,
short story writer, and <a href="/wiki/Poet" title="Poet">poet</a> of the <a
href="/wiki/American_Renaissance_(literature)" title="American Renaissance
(literature)">American Renaissance</a> period. His best known works include
<i><a href="/wiki/Typee" title="Typee">Typee</a></i> (1846), a romantic
account of his experiences in <a href="/wiki/Polynesia"
title="Polynesia">Polynesian</a> life, and his whaling novel <i><a
href="/wiki/Moby-Dick" title="Moby-Dick">Moby-Dick</a></i> (1851). His work
was almost forgotten during his last 30 years. His writing draws on his
experience at sea as a common sailor, exploration of literature and
philosophy, and engagement in the contradictions of American society in
a period of rapid change. He developed a complex, baroque style; the
vocabulary is rich and original, a strong sense of rhythm infuses the
elaborate sentences, the imagery is often mystical or ironic, and the
abundance of allusion extends to biblical <a href="/wiki/Bible"
title="Bible">scripture</a>, myth, philosophy, literature, and the visual
arts.</p>
```

If this file is saved to `melville.txt`, one can simply run `detag
melville.txt` or `cat melville.txt | detag` to print the contents of the
file with all tags removed and all entities decoded.

The following command is even more useful (\*nix systems only):

```bash
detag melville.txt | fmt
```

... it produces the following output:

```text
Herman Melville\[a] (August 1, 1819 – September 28, 1891) was an
American novelist, short story writer, and poet of the American
Renaissance period. His best known works include Typee (1846),
a romantic account of his experiences in Polynesian life, and his
whaling novel Moby-Dick (1851). His work was almost forgotten during his
last 30 years. His writing draws on his experience at sea as a common
sailor, exploration of literature and philosophy, and engagement in
the contradictions of American society in a period of rapid change. He
developed a complex, baroque style; the vocabulary is rich and original,
a strong sense of rhythm infuses the elaborate sentences, the imagery
is often mystical or ironic, and the abundance of allusion extends to
biblical scripture, myth, philosophy, literature, and the visual arts.
```

Multiple file arguments can be specified, and the output will be printed as
one blob of text.

## Use

Admittedly, this tool is not as sophisticated as a full HTML-to-text
converter.  It's really just a nifty toy.  You might use it in a simple
shell script or as a filter for some nasty lines of  markup in your favorite
text editor.
