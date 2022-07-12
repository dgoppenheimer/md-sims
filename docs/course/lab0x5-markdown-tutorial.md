# Lab0x5: Markdown Tutorial

## Work-Arounds for Markdown in Colab

### Footnotes

From this stack**overflow** post on [Footnotes in Markdown: both on Jupyter and Google Colab](https://stackoverflow.com/questions/61139741/footnotes-in-markdown-both-on-jupyter-and-google-colab)

```html
Example of footnote.<a name="cite_ref-1"></a>[<sup>[1]</sup>](#cite_note-1)
Example of footnote.<a name="cite_ref-2"></a>[<sup>[2]</sup>](#cite_note-2)


<a name="cite_note-1"></a>1. [^](#cite_ref-1) footnote 1
<a name="cite_note-2"></a>2. [^](#cite_ref-2) footnote 2
```

I changed the return icon to something more appealing to me:

```html
Example of footnote.<a name="cite_ref-1"></a>[<sup>[1]</sup>](#cite_note-1)

<a name="cite_note-1"></a>1. [&#8617;](#cite_ref-1) footnote 1
```

Which renders to:

Example of footnote.<a name="cite_ref-1"></a>[<sup>[1]</sup>](#cite_note-1)

<a name="cite_note-1"></a>1. [&#8617;](#cite_ref-1) footnote 1
