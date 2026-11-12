# Roadside Collective brand guidelines

**Last updated:** 11 November 2026

This is the working brand reference for anything built in this repo, including anything built by an AI tool. If you are generating a page, a component or an image for Roadside Collective, follow this file. Where this file and a design instinct disagree, this file wins.

Source: the Brand Bible, updated 18 October 2026, plus the four brand slides built on 23 October 2026. The palette and the type here are the same values the Python asset scripts use, so posters, social cards and the website cannot drift apart.

## What Roadside Collective is

A not for profit community in Brighton. We host watch parties in local pubs for women's professional cycling. More viewers attract more sponsors, which means better pay and more racing for women riders. Everyone is welcome and no cycling knowledge is needed.

**Tagline:** Watch women race. It makes a difference.

**The three pillars**

| Pillar | What it means | How it shows up |
| --- | --- | --- |
| **Watch** | Come together to watch women race | Watch parties, starting in Brighton pubs |
| **Follow** | We help you follow the season, the riders, the stories and the issues | The Cycling by Yoyo blog: race previews and reactions, rider spotlights, explainers, where to watch |
| **Belong** | No knowledge needed, everyone welcome | Friendly events, plain language, men welcome too |

**Positioning.** Cycling Weekly, Cyclingnews, Rouleur, British Cycling, Strava and Zwift all report the racing or help you ride. None of them bring people together in person to watch women race.

**The name, and the rule that goes with it.** Roadside Collective, settled 12 November 2026. No "cycling" in the name.

"Roadside" names where the fans stand, which is why the logo is called "Banner at the roadside". It describes the people rather than the venue, so it survives the pub and still fits when the meetups go to real races.

**The name never appears naked.** On its own, "Roadside" can read as roadside assistance. The fix is the descriptor, which always travels with it:

> Roadside Collective. Watch parties in Brighton for women's pro cycling.

Use it in the Instagram bio, the page title, the Eventbrite organiser name, the email footer and the flyer. Anywhere the name introduces itself to somebody new, the descriptor is next to it.

**Who it is for.** Everyone. This matters because the project used to be something else. An earlier version was a community for women, trans and non binary people who rode together. Roadside Collective is open to everyone, men included, and it does not organise rides. Do not reintroduce the old wording.

## Colours

| Colour | Hex | Use it for | Contrast |
| --- | --- | --- | --- |
| Deep purple | `#3D1E6D` | Main backgrounds, and text on light grounds | 12.2:1 with cream |
| Cream | `#FFF6E9` | Light backgrounds, and text on purple | 12.2:1 with purple |
| Flame orange | `#FF6B35` | Accents and highlights, **on purple or ink only** | 4.6:1 on purple, 6.1:1 on ink |
| Ink | `#1A1A1A` | Body text on cream | 16.3:1 with cream |

Four colours. Keep to them so every poster, post and page matches.

### The one rule that is never broken

**Never put flame orange on cream, or on white.** It is 2.65:1 and it fails WCAG AA for text. This is the single easiest brand mistake to make, because orange on cream looks warm and inviting in a thumbnail and is unreadable at body size.

What to do instead, when a cream section needs an orange accent:

- Use orange as a **solid block** with **ink text sitting on it**. That is what the logo does with the roadside banner, so it is already the brand's own treatment.
- Or use purple for the accent and keep orange for the purple sections.

A decorative orange rule or edge bar on cream is acceptable, because no text depends on it. An orange heading, an orange link, or orange body text on cream is not.

### Suggested CSS custom properties

```css
:root {
  --rc-purple: #3D1E6D;
  --rc-cream:  #FFF6E9;
  --rc-orange: #FF6B35;
  --rc-ink:    #1A1A1A;
}
```

Safe pairings, and these are the only ones to use:

| Ground | Text | Accent allowed |
| --- | --- | --- |
| `--rc-purple` | `--rc-cream` | `--rc-orange` |
| `--rc-cream` | `--rc-ink` or `--rc-purple` | `--rc-purple`, or orange blocks carrying ink text |
| `--rc-ink` | `--rc-cream` | `--rc-orange` |

## Type

| Role | Font | Notes |
| --- | --- | --- |
| Headlines and the wordmark | Big Shoulders Display, weight 800 to 900, **capitals** | Sporty, like a race number |
| Body text | DM Sans | Clear and friendly |

Both are free Google Fonts under the SIL Open Font Licence 1.1. Copies are in `assets/fonts/`, see the README there.

```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Big+Shoulders+Display:wght@800;900&family=DM+Sans:opsz,wght@9..40,400;9..40,700&display=swap" rel="stylesheet">
```

Headlines are set in capitals and tight. Big Shoulders Display is a condensed face, so it takes a much larger point size than it looks like it should. Do not set body text in it.

Body text is at least 16px on mobile.

## Logo

**Mix 3, "Banner at the roadside".** ROADSIDE in ink on a slanted flame orange banner, like the ones fans hang along the road, over a strip of road with a dashed orange centre line, and COLLECTIVE underneath. The profile picture is RC on the banner with the road line below.

**The logo is never redesigned, only converted.** If a different size, format or background is needed, convert one of the existing files in `assets/logo/`. Do not regenerate it, do not redraw it, and do not ask an image model for "a logo like this one". The files in this repo are the logo.

The dashed orange road line is the brand's spare part. It can be used on its own as a rule or a divider, which is what the posters and the social cards do.

## Voice

- Plain and warm, like a friendly club mate. Short sentences, no jargon.
- Everyone is welcome, men too. Never assume cycling knowledge, explain the racing instead.
- UK spelling. "We" for the collective, "you" for the reader.
- Say what a race is and why it matters before naming riders or teams.
- **No em dashes or en dashes.** Use commas or full stops.
- Never invent a statistic, a result or a rider's record. If a number is not checked, it does not go on the page.

**The objection the writing exists to answer** is not "what is cyclo-cross". It is "will I be the only one there who does not know anyone". Reassurance beats information nearly every time: it is free, you do not need to know anything about cycling, you do not need to bring anyone, nobody is in lycra.

## Accessibility, which is a brand rule here and not an extra

- Alt text on every image, without exception.
- All text meets WCAG 2.1 AA contrast. The palette table above gives the ratios, and the orange rule is the one that catches people out.
- Every control reachable and operable by keyboard, with a visible focus state.
- Headings in order, one h1 per page.
- Body text at least 16px on mobile.

## Still open

These are known gaps, recorded here so nobody assumes they are settled.

1. **The AI disclosure line.** The rule is agreed and the wording is not. Any AI generated image published by Roadside Collective carries it. See `assets/images/ai-generated/`.

   **Draft, for Joanna to approve or rewrite.** Three forms, because one length does not fit a caption, an alt text and a website footer.

   | Where | Wording |
   | --- | --- |
   | An Instagram caption, at the end | `Illustration, made with AI. Not a photo of the venue.` |
   | Inside alt text, after the description | `... This is an AI generated illustration, not a photograph.` |
   | A website or a poster footer | `Some images on this page are AI generated illustrations. Photographs of our events are real and are taken by us.` |

   Why it is worded this way. It says **illustration**, not "artwork" or "image", because illustration already tells a reader it is not evidence. It says **not a photo of the venue** because that is the specific thing a reader could otherwise be misled about, and a general disclosure that does not name the risk does not remove it. It is plain and short, so it fits the voice, and it goes at the end so it does not open a post with an apology. The site version distinguishes generated images from real event photographs, which protects the photographs, and those are the ones that matter.
2. **Mission, vision and the five values.** First draft only, and it lives outside this repo.
3. ~~Whether "cycling" belongs in the name.~~ **Closed 12 November 2026. The name stays Roadside Collective.**
