# Roadside Collective

Watch parties in Brighton for women's professional cycling. No cycling knowledge needed, everyone welcome.

> Watch women race. It makes a difference.

This repository is the start of the Roadside Collective website. Right now it holds the brand guidelines, the logo files, the fonts and the product requirements for the first page. There is no site in here yet.

## If you are an AI tool reading this

**Read [BRAND.md](BRAND.md) before generating anything.** It holds the palette, the type, the logo rules and the voice, and it is the authority for all of them.

The three things most often got wrong:

1. **Flame orange `#FF6B35` never goes on cream or white.** It fails WCAG AA at 2.65:1. On a cream section, use orange only as a solid block with ink text on it, the way the logo does, or use purple for the accent instead.
2. **The logo is never redesigned, only converted.** Use the files in `assets/logo/`. Do not generate a new one, and do not produce "something similar".
3. **No em dashes or en dashes** in any copy. Commas or full stops.

## What is in here

| Path | What |
| --- | --- |
| `BRAND.md` | The brand guidelines. Palette, type, logo, voice, accessibility |
| `assets/logo/` | The logo, as SVG and PNG, for light and dark grounds. See its README for which file to use |
| `assets/fonts/` | Big Shoulders Display and DM Sans, both SIL OFL 1.1 |
| `assets/images/` | Images cleared for use |
| `assets/images/ai-generated/` | Images made in Google AI Studio. Usable, but they carry the AI disclosure line and must never be captioned as the venue. See the README in that folder |
| `docs/` | Product requirements for the landing page |

## The project, in short

Not for profit, volunteer run, no budget, about two days a week. The only unavoidable cost is a domain name.

- **The first watch party** is Sunday 13 December 2026, showing a round of the UCI Cyclo-cross World Cup, in a Brighton pub. The pub is not booked yet, so the venue and the time appear as `[VENUE]` and `[TIME]` placeholders in every document here. Nothing with a bracket in it is ready to publish.
- **The target** is twenty people through the door, fifteen of them not personal friends.
- **The blog** is Cycling by Yoyo, on Substack, and it stays on Substack.
- **Signups** go through Eventbrite's free tier. The site points at it rather than replacing it.

## What the site has to do

The full requirements are in `docs/`. The short version is that someone who has just scanned a poster in a bike shop window, or tapped a link in an Instagram bio, needs to find the next watch party, understand what it is, and sign up, in under a minute on a phone.

The thing it must not get wrong is the email capture. The only live page today is a Mailchimp page with a signup button and no email field, so everyone who tries to say yes is currently lost at that moment.

## Status

Pre build. The platform decision is Lovable. Nothing is deployed and no domain is connected.

## Licence

The copy, the design and the logo are Roadside Collective's and are not for reuse. The two fonts are redistributed under the SIL Open Font Licence 1.1, see `assets/fonts/README.md`. See [LICENCE.md](LICENCE.md).
