# The Lovable build prompt

The prompt that builds the landing page. Kept here so it travels with the project,
and so the next version of the page can be built from the same starting point rather
than from memory. The full version, with the reasoning behind every constraint and
the review criteria, is in `CRISPE Prompts/Lovable Watch Party Landing Page.md` in
the AI Bootcamp repo.

## Before pasting it

1. **Connect this repository through Lovable's GitHub integration.** Pasting the URL
   into a chat message does not give it file access, and this repo is private. Connect
   it to this existing repo, not to a new empty one, because the brand files are the
   reason the repo exists.
2. **The brand is inlined in the prompt anyway**, so the page is still correct if
   Lovable never opens `BRAND.md`.
3. **If the logo does not appear**, drag `assets/logo/roadside-collective-logo-on-cream.svg`
   and `assets/logo/roadside-collective-profile-picture.svg` into the chat. That is a
   conversion, which is allowed. Letting it draw a replacement is not.

## The prompt

```
C, Capacity and Context
I run Roadside Collective, a volunteer run not-for-profit in Brighton. We host watch
parties in local pubs for women's professional cycling. Everyone is welcome and no
cycling knowledge is needed. The tagline is "Watch women race. It makes a difference."

The brand already exists and is in the connected repository,
https://github.com/JoannaKmiec11/roadside-collective. Read BRAND.md before you write
any code. The logo files are in assets/logo/ and the fonts are in assets/fonts/.

In case you cannot read those files, here is everything you need, and it is not
negotiable either way:

  Deep purple #3D1E6D   backgrounds, and text on light grounds
  Cream      #FFF6E9   light backgrounds, and text on purple
  Flame orange #FF6B35 accents, ON PURPLE OR INK ONLY
  Ink        #1A1A1A   body text on cream

  Headlines and the wordmark: Big Shoulders Display, weight 800 to 900, CAPITALS.
  Body text: DM Sans. Both are in assets/fonts/ as variable TTFs.

  Logo: assets/logo/roadside-collective-logo-on-cream.svg for light sections,
  roadside-collective-logo-on-purple.svg for dark ones.

Do not invent a palette, a typeface or a logo. Do not generate a logo of any kind.

The first watch party is Sunday 13 December 2026, showing a round of the UCI
Cyclo-cross World Cup. The target is twenty people through the door, fifteen of them
not personal friends.

Most visitors will arrive on a phone, from an Instagram bio link or from a poster in
a bike shop window. Almost none of them know anything about professional cycling.

R, Role
Act as a front end engineer building one marketing page for a volunteer who has no
budget, no designer and about two days a week. You are building the only page, not
the first of several. Favour one page that works on a phone over anything clever.

I, Insight and Instruction
Build a single page, in this order top to bottom.

1. Hero. The logo, the tagline "Watch women race. It makes a difference.", and the
next watch party as date, venue and time, then a primary button that goes to the
Eventbrite signup. On a 390 pixel wide phone the date, the venue, the time and the
button must all be visible without scrolling.

2. What this is, in two sentences, in plain English. No mission statement.

3. The reassurance block. This is the most important section on the page and it must
come before anything else about cycling. Four plain statements, each on its own line
with room around it: it is free, you do not need to know anything about cycling, you
do not need to bring anyone, nobody is in lycra. Then one short paragraph describing
the first five minutes: you arrive, there is a table with a Roadside Collective sign
on it, somebody says hello, you get a drink, you sit down.

4. Email signup. A visible label, an email field, a submit button, an inline
confirmation message and an inline error message. A link to the privacy notice next
to the form, not in the footer.

5. From the blog. Three cards linking to recent posts on our Substack, Cycling by
Yoyo, each with a title and a date, hardcoded for now. Feature the most recent one
larger than the other two.

6. Footer. A contact email address for pub landlords, bike shops and sponsors. The
privacy notice. Links to Instagram and Substack.

Use these exact placeholders wherever the real value is not yet known, including the
brackets: [VENUE], [TIME], [LINK], [SITE URL], [HANDLE], [CONTACT EMAIL]. Do not
invent a pub name, a street, a start time or a URL. Do not replace a placeholder with
something plausible.

Put every piece of copy and every event detail in one clearly commented config file
at the top of the project, so the date, the venue and the time can be changed in one
place without touching a component.

If no event is scheduled, the hero shows "Next date coming soon" with the email
signup in place of the Eventbrite button. It never shows an empty block or a date
that has passed.

S, Specification
React with Tailwind, which is your default. One page. No router, no CMS, no backend,
no user accounts, no database.

Load Big Shoulders Display and DM Sans from the files in assets/fonts/ rather than
from Google's servers, so the page does not send visitors' IP addresses to Google and
the privacy notice can stay short.

For the email form, use a form service with a free tier, Formspree or equivalent, and
put the endpoint in an environment variable. Tell me in your summary exactly where to
paste the endpoint.

Favicon and social share image: convert assets/logo/roadside-collective-profile-
picture.svg. Converting is allowed, redesigning is not.

Give me a short summary at the end listing: where the config file is, where the form
endpoint goes, and anything you could not do.

P, Personality and Parameters
Voice: plain and warm, like a friendly club mate. Short sentences. No jargon. UK
spelling. "We" for the collective, "you" for the reader. Never assume any cycling
knowledge.

Never use em dashes or en dashes. Use commas or full stops.

Colour rules, from BRAND.md, and the first one is absolute:
- Flame orange #FF6B35 never appears on cream #FFF6E9 or on white. It is about
  2.65:1 and it fails WCAG AA. When a cream section needs an orange accent, use
  orange as a solid block with ink #1A1A1A text on it, which is what the logo does,
  or use deep purple #3D1E6D for the accent instead.
- Deep purple #3D1E6D grounds carry cream #FFF6E9 text and may use orange accents.
- Cream grounds carry ink #1A1A1A or deep purple text.

Accessibility is a requirement and not a polish pass. Alt text on every image. All
text meets WCAG 2.1 AA. Every control keyboard reachable with a visible focus state.
Headings in order with exactly one h1. Body text at least 16px on mobile.

Do not add a stock photograph of a cyclist. Do not add a hero background image at
all. There is no photograph of the venue yet and a generated one would be dishonest,
because the page exists to tell someone what the room will actually be like.

Do not add a countdown timer, a newsletter popup, a cookie banner, a testimonials
section, a sponsors logo strip, or an "our story" section. None of them exist yet and
an empty one is worse than none.

E, Example
The tone to aim for, which is real copy from our Instagram:

"You arrive at [VENUE] from [TIME]. There is a table with a Roadside Collective sign
on it. You say hello, you get a drink, you sit down. The racing goes on the big screen.
It is about an hour. Afterwards people stay or people go, both are completely fine.

Nobody is in lycra. Nobody is going to test you. Several of us will be looking it up
on our phones."

That is the register for the whole page. Warm, specific, and slightly understated.
Not "Join the movement."
```

## Follow up prompts, one at a time

Lovable works better on one change per message than on a list, and a single change is
far easier to undo when it is wrong.

```
1. Show me the page at 390 pixels wide. Is the date, the venue, the time and the
   signup button all visible without scrolling? If not, fix it by reducing the
   logo and the tagline, not by removing the venue.

2. Check every colour pair on the page against WCAG AA and list the ratios. Tell me
   if flame orange appears anywhere on a cream or white ground.

3. Add the inline error state for an invalid email address. Plain language, next to
   the field, not an alert box. Submitting twice must not create two entries or
   break the page.

4. Move every string on the page into the config file. Then show me the config file
   on its own, so I can see that changing the venue is one edit.

5. Add the privacy notice as a section on the same page, not a new route. What the
   address is used for, that it is shared with nobody, and how to unsubscribe.

6. Tab through the page from the top and tell me the focus order, and whether every
   control has a visible focus state.
```

## After the build

Record what happened in the CRISPE prompt file, under "Review of the output". The six
checks are already written down there, decided before the run so the review is not
written to flatter the prompt. The two that matter most: did it put orange on cream
anywhere, and did it invent a venue, a time or a URL.
