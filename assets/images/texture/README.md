# Brand texture

Flat brand purple deepening into a gradient, a very faint spoked wheel, and
the dashed orange road line. Same furniture as the Trello board background and
the video plates, so everything matches.

| File | Size | For |
| --- | --- | --- |
| `brand-texture-band-1920x520.jpg` | 1920 x 520 | A full width band between sections |
| `brand-texture-square-1400.jpg` | 1400 x 1400 | A square panel, if one is ever needed |

JPEG rather than PNG on purpose. The gradient needs a little noise to stop it
banding on screen, and that noise makes a PNG four times larger for no visible
gain.

## No logo on these

The Trello version carries the wordmark bottom right, because a board has
nothing else on it to say whose board it is. **These do not**, because the
website already shows the logo in the header, and a background carrying it as
well puts the name on screen twice in one viewport.

Built by `Roadside Collective/Trello/make_trello_bg.py` in the AI Bootcamp
repo, which now takes `with_logo=False` and an `out` directory. The Trello
files it produces are unchanged.

## Not for the hero

This was tried as the hero image and it is the wrong tool for that job. A hero
has about three seconds to tell a stranger what this is, and a purple field
with a faint wheel tells them nothing. On a Trello board the same image is
right, because the cards carry the content and the background has to stay
quiet.

The hero keeps a picture of people watching a race in a pub, because that is
the whole proposition in one image. This is for the quiet bands between
sections, where there is already text doing the talking.
