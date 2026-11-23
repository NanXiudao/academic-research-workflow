# Academic Research Workflow

A version-controlled collection of configuration notes, templates, and integration guides for an academic literature workflow built around **Zotero 10**, **Obsidian**, **ZotLit 2.2**, and **Zotero Style**.

> **Status:** Working setup notes from a manually tested personal workflow. Exact ZotLit paper-note template content and plugin-specific settings were not fully preserved; draft examples are explicitly marked.

## Components

| Component | Purpose | Documentation |
|---|---|---|
| Zotero 10 | Literature metadata, PDF reading and annotations | [Zotero](zotero/README.md) |
| Zotero Style | Custom tag column and UI adjustments | [Zotero Style](zotero/zotero-style.md) |
| ZotLit 2.2 | Import paper notes and annotations into Obsidian | [ZotLit](zotlit/README.md) |
| Obsidian | Markdown paper notes and callout display | [Obsidian](obsidian/README.md) |
| Zotero Drop Callout | Automatically format Zotero PDF highlight drops | [Integration](integrations/zotero-drop-callout.md) |

## Verified workflow

1. Add a paper to Zotero and retrieve metadata using its DOI.
2. Open the paper in Zotero's built-in PDF reader and highlight a passage.
3. Drag the highlight directly into an editable Obsidian note.
4. The separately maintained **Zotero Drop Callout** plugin formats the insertion as a page-aware Markdown callout.
5. Click **Open PDF** to navigate back to the source annotation in Zotero.

## Example output

```markdown
> [!quote] PDF Highlight · Page 3
>
> In RBO, we test the optimization performance...
>
> [📄 Open PDF](zotero://open-pdf/library/items/HGACVREL?page=3&annotation=L5RV6EX5) · (Tom 等, 2025, p. 3)
```

The item and annotation IDs above are examples.

## Quick setup

1. Install Zotero 10 and Obsidian.
2. Install the ZotLit and Zotero Style plugins where appropriate.
3. Configure Zotero's native highlight template from [zotero/templates/highlight.html](zotero/templates/highlight.html).
4. Install [Zotero Drop Callout](https://github.com/NanXiudao/zotero-drop-callout) in Obsidian.
5. Configure ZotLit templates using [zotlit/README.md](zotlit/README.md), and preserve a backup of any existing working template before making changes.
6. Optionally apply the [Zotero Style UI adjustment](zotero/zotero-style.md).

## Repository conventions

- **Verified:** observed working in the Zotero 10 / Obsidian workflow discussed during setup.
- **Reference:** documented configuration idea or template requiring local validation.
- **Optional:** a cosmetic change or personal preference.
- Never commit a real Zotero database, private library data, Obsidian vault content, credentials, or tokens.

## Related project

**[Zotero Drop Callout](https://github.com/NanXiudao/zotero-drop-callout)** is developed independently. This repository documents how to integrate it and does not duplicate its source.

## License

MIT for original documentation and configuration examples. Third-party plugins retain their respective licenses.
