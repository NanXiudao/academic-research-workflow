# Zotero 10

## Verified setup

- DOI-based metadata retrieval was working.
- Zotero's built-in PDF reader was used to highlight papers.
- Native PDF annotation drag-and-drop into Obsidian was working.
- The native highlight note template was customized to produce an Obsidian-compatible callout.

## Native annotation template

See [templates/highlight.html](templates/highlight.html).

In Zotero's advanced preferences, locate:

```text
extensions.zotero.annotations.noteTemplates.highlight
```

Back up the existing value before replacing it. Restart or reopen the relevant editor if needed and test with a single highlight.

The `{{highlight quotes='false'}}` placeholder renders the highlighted text without surrounding quotation marks. Zotero may still append a deep link to the PDF annotation when dragged into Obsidian. The companion Obsidian plugin normalizes that link.

## Limitations

Zotero's native note-template expressions support placeholders and conditional logic, but this configuration does not rely on undocumented string-processing functions. Citation style and locale are controlled by Zotero's citation settings.
