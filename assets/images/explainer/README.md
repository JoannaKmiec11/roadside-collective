# Cyclo-cross explainer cards

Three square cards for the "What we are watching" section, built from the
brand palette and fonts in Python. Not AI images, which is why they are not in
`ai-generated/`.

| File | Says |
| --- | --- |
| `explainer-format-1080.png` | A lap race, in winter, in a field |
| `explainer-running-1080.png` | They pick the bike up and run |
| `explainer-hour-1080.png` | About an hour, start to finish |

## They are not the Instagram cards

The Tuesday 8 December carousel says the same three things, and those versions
were tried here first. They carried three things that only work in a feed:

1. **A counter**, 2/5, 3/5, 4/5, referring to a swipe order that does not
   exist on a web page with three cards on it.
2. **Kickers** reading "ONE, THE FORMAT" and so on, same problem.
3. **The ROADSIDE COLLECTIVE wordmark** on every card. On Instagram a post
   travels away from the account and has to carry the name. On the brand's own
   site the logo is already in the header, so it was the name three more times
   for nothing.

Dropping all three freed enough room to go square, which suits a row of three
on a wide screen far better than 4:5, where three tall cards push everything
below them off the screen.

## They need the purple band behind them

They are cream, and the page is cream. On a cream ground they vanish, which is
what happened first time: the build tool compensated by outlining each one in
purple, which is a patch on a symptom.

**The section they sit in has a deep purple `#3D1E6D` background**, which is
what makes them read as solid blocks and is why they need no outline. If that
band is ever removed, these cards stop working and the fix is the band, not an
outline.

## Rebuilding

`Roadside Collective/Launch Campaign/make_web_explainer_cards.py` in the AI
Bootcamp repo. The wording is a list at the top. All three share one headline
size, computed as the largest that fits every card, so the row reads as a set.
