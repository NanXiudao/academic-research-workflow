# ZotLit 2.2

## Verified workflow capabilities

ZotLit was connected to Zotero and used to generate paper notes in Obsidian. The working paper-note template included:

- bibliographic metadata and abstract;
- research questions;
- methodology;
- experiments;
- a dynamic annotations section using ZotLit query features.

The exact full paper-note template was not preserved. Avoid replacing an existing working template with a reconstructed guess.

## Annotation drag template

ZotLit's **Template Workbench → Annotation (标注)** supports Liquid-like syntax and the following fields used in the working setup:

- `zt.text`: highlighted text;
- `zt.pageLabel`: page label;
- `zt.backlink`: source annotation link;
- `zt.citation`: citation text;
- `zt.comment`: annotation comment;
- `zt.imgLink`: image link for image annotations.

See [templates/annotation-reference.md](templates/annotation-reference.md) for a **reference draft**, which must be validated in the local Template Workbench.

## ZotLit vs native Zotero drag

ZotLit annotation drag uses the ZotLit annotation template. Dragging a highlight directly from Zotero's built-in PDF reader uses Zotero's native annotation template and the Obsidian-side Zotero Drop Callout plugin. These are separate configuration paths.
