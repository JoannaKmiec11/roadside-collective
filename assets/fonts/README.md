# Fonts

The two Roadside Collective brand fonts, kept in the repo so a build does not
depend on a download or on a web font request at runtime.

| File | Font | Axes |
| --- | --- | --- |
| `BigShouldersDisplay.ttf` | Big Shoulders Display | `wght`, used at 800 to 900 |
| `DMSans.ttf` | DM Sans | `opsz`, `wght`, used at 400 and 700 |

Both are variable fonts, so weights are set on the axis rather than faked by
the browser. Headlines are Big Shoulders Display in capitals. Body text is
DM Sans, and never Big Shoulders.

## Licence

Both are published by Google Fonts under the **SIL Open Font Licence, Version
1.1**, which is what the `ofl/` path in their source URLs means. The OFL allows
redistribution in a repository like this one, including bundling them with a
website, provided the licence travels with them.

Sources, which are the exact files in this folder:

- https://github.com/google/fonts/raw/main/ofl/bigshouldersdisplay/BigShouldersDisplay%5Bwght%5D.ttf
- https://github.com/google/fonts/raw/main/ofl/dmsans/DMSans%5Bopsz,wght%5D.ttf

**To do:** copy the full `OFL.txt` from each font's folder in the Google Fonts
repository into this directory as `OFL-BigShouldersDisplay.txt` and
`OFL-DMSans.txt`. The licence requires the full text to be distributed with the
fonts, and summarising it here is not a substitute. It has deliberately not
been pasted in from memory, because a licence file has to be the real text.

## Using them on the web

Either serve these files, or load the same fonts from Google Fonts. The link
tag is in BRAND.md. Loading from Google Fonts sends the visitor's IP to Google,
which is worth a line in the privacy notice. Self hosting these files avoids
that, and it is the better option for a page whose privacy notice is meant to
be short.
