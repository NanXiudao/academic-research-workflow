# Zotero → Obsidian: automatic PDF highlight callouts

**Companion plugin:** https://github.com/NanXiudao/zotero-drop-callout

## Installation

Install the companion plugin in:

```text
<Obsidian vault>/.obsidian/plugins/zotero-drop-callout/
```

The folder should contain `main.js` and `manifest.json`. Enable the plugin under Obsidian's Community plugins settings.

## Configuration

1. In Zotero 10, back up and configure the native highlight note template: [highlight.html](../zotero/templates/highlight.html).
2. Enable Zotero Drop Callout in Obsidian.
3. Open an editable Markdown note.
4. Drag one highlighted passage from Zotero's PDF reader into the note.
5. Verify the callout title, text, single PDF link and citation.

## Verified outcome

The Obsidian plugin removes the inline `([pdf](zotero://open-pdf/...))` label and moves the deep link to the footer as `Open PDF`. It also removes a duplicate `Open PDF` label that may already exist in the Zotero native template.

The page number comes from the `page` URL parameter. The annotation ID is preserved so Zotero can navigate to the exact annotation.

## Troubleshooting

- **No conversion:** Check the plugin is enabled, the drop happens inside an editable note, and the inserted Markdown contains a `zotero://open-pdf/` link.
- **Two Open PDF labels:** Verify you are using the current companion plugin, not an earlier v0.1.0 copy.
- **Different author/year formatting:** Adjust Zotero citation style and locale; the plugin preserves citation text.
- **No PDF navigation:** Verify Zotero is installed and registered as the handler for `zotero://` links.
