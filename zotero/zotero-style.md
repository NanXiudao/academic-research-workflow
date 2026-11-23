# Zotero Style configuration

## Custom tag column

The Zotero Style plugin was used to configure a custom tag display column. The exact tag column expression was not preserved in this repository. Export the working configuration from your own installation before attempting to recreate it.

## Hide the pink Graph View toolbar button (verified)

The toolbar element was identified with the selector `#zoterostyle`.

1. Open Zotero's profile directory.
2. Create `chrome/userChrome.css` if it does not exist.
3. Add the CSS from [userChrome.css](userChrome.css).
4. In advanced preferences, set `toolkit.legacyUserProfileCustomizations.stylesheets` to `true`.
5. Restart Zotero.

This is a UI-only customization. It hides the matching toolbar element and does not uninstall Zotero Style.

## Theme

A Catppuccin theme was explored. Exact theme values were not preserved, so no theme preset is claimed as verified.
