# Roadside Collective watch party signup page (PRD)

**Author:** Joanna
**Contributors:** Lucas (tutor, Project Week review)
**Version:** 1.0
**Date:** 11 November 2026
**Status:** draft, for build in the week commencing 16 November 2026
**Hard deadline:** live by Sunday 22 November 2026, because the flyer goes to print after it and has to carry the address

## A note on this template, read this first

This is written to an **AI Product** PRD template, and the product is a one page website. There is no model in it, and there will not be one in v1.

I have not stretched the AI sections to make it look like there is. Inventing a chatbot nobody asked for, to satisfy a heading, is how a project loses three weeks it does not have before an event that is already booked.

What I have done instead is answer the template's own question honestly. **How can we use AI to help our users?** For this product, in this phase, the answer is that AI does not touch the user. It does three things behind them, all of which are real and two of which already exist:

1. **It builds the page.** Lovable generates the site from the brand files in this repository.
2. **It runs the content pipeline** that sends people to the page. One long article a week, with the Instagram posts cut out of it.
3. **It records who turned up**, through the Base44 door check in app, which closes the measurement gap this product otherwise ends with.

Section 4 sets out what would have to be true before a model ships to users, so that the decision is a judgement with criteria attached rather than an omission. See **Leveraging AI**.

## Relevant documents

| Document | What it holds |
| --- | --- |
| [BRAND.md](../BRAND.md) | Palette, type, logo rules, voice, accessibility. The authority for all of them |
| `Roadside Collective/Launch Campaign/User Journey - Tuesday Cyclo-cross.md` | The worked journey from an Instagram post to a signup. Feeds section 5 |
| `Roadside Collective/Launch Campaign/7 Day Content Plan.md` | The seven days before the event, post by post |
| `CRISPE Prompts/Lovable Watch Party Landing Page.md` | The build prompt |
| `CRISPE Prompts/Roadside Collective Business Roadmap.md` | Phases 1 to 5, Oct 2026 to Dec 2027 |
| `Week 2/Assignments/Base44 Door Check-in - Build.md` | The attendance app, which owns the North Star measurement |
| `Roadside Collective/Launch Campaign/Website PRD.md` | The earlier requirements document, superseded by this one. Kept for the decision history |

Everything written against `[VENUE]`, `[TIME]`, `[LINK]`, `[SITE URL]`, `[HANDLE]` and `[CONTACT EMAIL]` is a placeholder because the pub is not booked. Nothing with a bracket in it is ready to publish.

---

# 1. About

Roadside Collective is a volunteer run, not for profit community in Brighton that hosts watch parties in local pubs for women's professional cycling. More viewers attract more sponsors, which means better pay and more racing for women riders. Everyone is welcome and no cycling knowledge is needed.

The first watch party is Sunday 13 December 2026. The target is twenty people through the door, fifteen of whom are not personal friends.

**The TLDR.** Roadside Collective has no home of its own. The only live page is a Mailchimp landing page with a signup button and no email field, so it collects nothing. Every person the posters, the flyer and Instagram send there is lost at the exact moment they try to say yes. This product is one page that takes that person and turns them into either a signup or an email address, in under a minute, on a phone.

The problem space is not awareness. It is **conversion, and specifically the conversion of a stranger**. Friends will come because they were asked. The project only works if people who were not asked turn up, and those are the people who need somewhere to check that this is real before walking into a pub alone.

# 2. Market insights

## Competitor analysis

The market for cycling media is saturated. The market for **watching women's racing together, in person, in the South East** has nobody in it.

| Who | What they do | Why they are not this |
| --- | --- | --- |
| Cycling Weekly, Cyclingnews, Rouleur | Report the racing | You read them alone |
| British Cycling | Governs and organises riding | Participation, not spectating |
| Strava, Zwift | Help you ride, and socially around riding | About your own riding, not about watching anyone else |
| Local cycling clubs, Neighbourhood Gravel | Organise rides | You have to own a bike and be able to keep up |
| Eventbrite, Meetup, Brighton what's on listings | Distribution | They list an event. They do not make anyone trust it |
| Rapha Clubhouse style brand spaces | Host screenings | Not in Brighton, brand led, and built for people already in the sport |

**The real competitor is staying at home.** Watching the race alone on a laptop is free, requires no social risk, and is what the target user does today. The page is competing with the sofa, not with Cyclingnews.

**Positioning line:** Cycling Weekly, Cyclingnews, Rouleur, British Cycling, Strava and Zwift all report the racing or help you ride. None of them bring people together in person to watch women race.

## Market analysis

Favourable, with one hard dependency.

- Women's professional cycling is growing in coverage and the audience is growing with it, but the broadcast is still fragmented across subscriptions, which is a barrier for a casual viewer and an argument for watching somewhere that already has the subscription.
- Brighton has a dense pub trade with sports subscriptions, an active cycling population and a strong appetite for local events, which is why the local hashtags do more work than the cycling ones.
- Grassroots free events lose roughly a third of signups between the form and the night, which is why thirty signups are needed for twenty attendees.
- **The dependency:** who holds UK broadcast rights for the 2026/27 Cyclo-cross World Cup decides which pubs can legally show it at all. This is the largest unresolved risk in the entire project and it sits outside this product.

## Technology analysis

What comparable organisations use, and what it means here.

| Approach | Who uses it | Read across |
| --- | --- | --- |
| Linktree or a Mailchimp landing page | Almost every small community account | Cheap and fast, but weak at the one job that matters, and it is the failure already in production here |
| Squarespace or Wix templates | Small clubs and venues | Good enough, but the brand fonts and the contrast rules are hard to hold, and it is a monthly cost against a zero budget |
| AI app builders: Lovable, Base44, v0 | Increasingly, solo founders | Generates a real, editable codebase from a prompt. Suits a single maintainer with no designer |
| Hand built static HTML | Technical founders | Total control, but every edit is a deploy |

**AI specific solutions in use by comparable organisations:** essentially none at the user facing layer. Community groups this size use AI to draft copy and generate images, not to serve features. That is a finding, not a gap to fill. It is consistent with the conclusion in section 4.

**The decision is Lovable.** It produces an editable React codebase in this repository rather than a locked template, it can be pointed at `BRAND.md` so the brand is given rather than described, and the build counts twice because it is also the Project Week piece agreed with Lucas. It supersedes the hand built recommendation in the earlier PRD, which is kept for the decision history.

## Customer segments

| Segment | Size, roughly | Why they matter |
| --- | --- | --- |
| **Curious strangers in Brighton** | The target, and the hardest | The project only proves itself if these people turn up. 15 of 20 |
| **Warm contacts** | Neighbourhood Gravel members, friends of friends | They fill the first room and they are not evidence of anything |
| **Gatekeepers** | Landlords, bike shops, potential sponsors | Never sign up, decide whether the project has a venue at all |
| Existing women's cycling fans | Small, and mostly not local | Nice to have. Not who the page is written for |

## User personas

**Primary persona, the one the page is built for.**

> **Nadia, 34, lives in Hanover, Brighton.** Rides a bike to work and nowhere else. Saw a poster in a bike shop window while collecting a repaired wheel, and has since seen one Instagram post.
>
> She has watched about ten minutes of professional cycling in her life, on a television in someone else's house. She likes the idea of women's sport getting a bigger audience and she has said so out loud. She has a free Sunday.
>
> **Her actual question is not "what is cyclo-cross".** It is "will I be the only person there who does not know anyone". She has been to one meetup before where everyone already knew each other and she left after twenty minutes, and she is not doing that again.
>
> She will decide in under a minute, on her phone, probably in a queue. If the page makes her read a mission statement before telling her what the night is like, she is gone.

Secondary, **the warm contact**: already wants to come, wants the date, the place and the link, fast, and resents being made to scroll.

Tertiary, **the gatekeeper**: a landlord deciding whether to hand over a back room. Never converts, and is still worth the page, because without them there is no event.

# 3. The problem

## Use cases

What users are trying to achieve, in priority order.

1. **Find out whether this event is for someone like me**, without having to ask anyone. Primary persona. The single most common use case and the hardest to serve.
2. **Find the date, the venue and the start time**, and get to a signup. All three personas.
3. **Register**, in a way that produces a reminder, because an event three weeks away is an event that gets forgotten.
4. **Leave contact details when the date does not work**, so that a person who is interested but busy is not lost permanently.
5. **Check that this is a real organisation** rather than one person's idea. Gatekeepers, and quietly, strangers too.
6. **Find out what is actually going on in women's racing**, which is the blog's job, and the page's job is to point at it.

## Pain points

| Use case | What goes wrong today |
| --- | --- |
| 1, is this for me | Nothing anywhere answers it. The posters and the Instagram bio have no room, and the one live page is a signup form with no reassurance on it at all |
| 2, find the details | They exist only inside individual Instagram posts, which scroll away. There is no stable address to put on a poster |
| 3, register | **The Mailchimp page has a signup button and no email field.** Everyone who tries to say yes fails, silently, and there is no record that they tried |
| 4, not free that day | No mechanism exists. That person is lost permanently, and they are the cheapest person to reach next time |
| 5, is this real | One Instagram account with few posts, no site, no contact address. A landlord has nothing to check |
| 6, the blog | Substack exists and nothing links to it from anywhere a stranger will land |

The compounding failure is **3**. Every pound of effort in the posters, the flyer, the bike shop round and the seven day content push is currently spent sending people to a form that cannot accept them.

## Problem statement

> **Curious Nadia wants to watch women's cycling with other people in Brighton, but she cannot find out whether she would be welcome or out of place, and when she decides to try anyway, the only page that takes signups has no email field, so she gives up and watches the race alone at home.**

## Hypotheses and mission statement

**Main hypothesis.** The barrier to attendance is social risk, not information. If a stranger is told plainly and early that it is free, that no cycling knowledge is needed, that coming alone is normal, and exactly what the first five minutes look like, then enough of them will convert that fifteen of the twenty people in the room on 13 December will not be personal friends.

**Secondary hypothesis.** A working email field is worth more than every other feature on the page combined, because it converts both the people who can come and the people who cannot.

**Mission statement for this product.** By giving Roadside Collective one honest, fast page of its own, we make deciding to turn up alone feel like a small thing rather than a risk, for people who have never watched a bike race in their lives.

# 4. The solution

## Ideation

Everything considered for the prioritised pain points.

- A one page site with the next event, a reassurance block and an email field
- A reassurance block written as the first thing after the hero, not buried
- A "what the first five minutes look like" narrative paragraph
- A photograph of the actual room
- The three most recent Substack posts, so the project visibly produces something
- A contact route for landlords and shops, separate from the signup
- A women's professional cycling calendar, with which races Roadside Collective is watching
- A countdown timer to the next party
- A map and travel directions
- A WhatsApp community link
- An FAQ section
- A chatbot that answers "what is cyclo-cross"
- Personalised race recommendations based on stated interests
- Automatic Substack feed by RSS
- A past events gallery with photographs

Cut, with reasons, because a cut list is more useful than an idea list: the **countdown timer** adds urgency to an event with no venue confirmed and reads as pressure. The **FAQ** is a way of avoiding writing the page properly. The **WhatsApp link** creates a space that has to be moderated by somebody who is also hosting. **Past events** needs a past. The **map** is a line of text until there is a venue. The two AI features are dealt with below.

## Leveraging AI

**AI is not appropriate at the user facing layer of this product, and this is the section that says so with reasons rather than quietly skipping it.**

The two AI features considered, and why both were cut:

| Idea | Why it was cut |
| --- | --- |
| A chatbot answering "what is cyclo-cross" | The question is already answered better by a 1,000 word article and a five card carousel that are written, checked and reusable. A chatbot would answer it worse, could invent a rider's palmares or a race result, and would need monitoring by one volunteer. It also answers the wrong question. The barrier is social risk, not knowledge |
| Personalised race recommendations | Requires users, preferences and a catalogue. There are no users. This is a Phase 3 idea at the earliest, and it belongs to the Cycling Planner product, not to a signup page |

**Where AI is genuinely essential to this work, and where the course learning actually sits.**

1. **It builds the product.** Lovable generates the codebase from a CRISPE prompt pointed at `BRAND.md`. Without it, a volunteer with no front end background does not ship an accessible, brand correct, responsive page in one week alongside booking a pub. This is the difference between the site existing and not existing.
2. **It runs the content engine that fills the page.** One Substack article a week, with the Instagram posts cut out of it. The Tuesday carousel is four cards lifted word for word from the Monday article. AI drafts and adapts, a human checks every fact, and the standing rule is that no statistic, result or rider record is ever invented.
3. **It closes the measurement loop.** The Base44 door check in app records who actually walked in, which is the only way the North Star metric in section 8 can be read at all. Eventbrite knows who registered. Nothing else knows who came.

**What would have to be true before a model ships to users.** All three, not any one:

- More than 200 people on the list, so that personalisation has anything to personalise from
- A repeating event schedule, so that a recommendation has somewhere to point
- A second volunteer, so that nobody is monitoring a generative feature while also hosting a party

Until then the honest answer to "how can we use AI to help our users" is that we use it to get the thing built and keep it fed, and we do not put it between the user and the information.

## Feature prioritisation

RICE. Reach is the percentage of the primary persona affected. Score is `(R x I x C) / E`.

| Feature | Reach | Impact | Confidence | Effort | Score |
| --- | --- | --- | --- | --- | --- |
| **Email capture that actually works** | 100% | 10 | 10 | 2 | **5000** |
| **Hero with the next event and a signup button** | 100% | 9 | 10 | 2 | **4500** |
| **Eventbrite link** | 60% | 7 | 10 | 1 | **4200** |
| **The reassurance block** | 90% | 8 | 8 | 2 | **2880** |
| **A photograph of the real room** | 80% | 8 | 9 | 2 | **2880** |
| Favicon and social share image | 70% | 4 | 9 | 1 | 2520 |
| Accessibility pass | 100% | 6 | 9 | 3 | 1800 |
| Privacy notice | 100% | 3 | 10 | 2 | 1500 |
| Custom domain | 100% | 5 | 9 | 3 | 1500 |
| Cookieless analytics | 100% | 3 | 7 | 2 | 1050 |
| Substack posts block | 40% | 5 | 7 | 2 | 700 |
| Contact route for gatekeepers | 10% | 7 | 9 | 1 | 630 |
| Women's pro cycling calendar | 30% | 6 | 4 | 9 | 80 |

**Three things RICE gets wrong here, and they are worth stating because the score is not the decision.**

- **The privacy notice scores 1500 and is non negotiable.** It is a UK GDPR obligation. RICE cannot see legal duty, only impact on conversion.
- **The photograph of the real room scores joint fourth and cannot be built**, because the pub is not booked. Score does not equal readiness.
- **The calendar scores 80 and is still the most distinctive thing on the site**, because no competitor does it. That is the difference between a conversion metric and a differentiation argument. It stays P1 and it is the first thing to wait if the week slips.

## AI MVP

**No.** There is no model in v1, for the reasons set out in **Leveraging AI** above.

The MVP is a static single page site. The nearest thing to a model in the stack is the generative step that produces the codebase, which runs once at build time and never at request time. No user input is ever sent to a model, which is also why the privacy notice stays short and why no cookie banner is needed.

## Roadmap

Aligned to the business roadmap phases.

| Phase | When | What ships | Gate to the next phase |
| --- | --- | --- | --- |
| **v1, this PRD** | by 22 Nov 2026 | Hero, reassurance block, email capture, Eventbrite link, Substack links, privacy notice, accessibility pass, share image, analytics | A tested signup, from an address Joanna does not own |
| **v1.1** | by 28 Nov 2026 | Custom domain connected, real venue photograph once the pub is confirmed | The flyer goes to print. Nothing can change the URL after this |
| **v1.2** | w/c 14 Dec 2026 | Photographs from the first party, the next date, a short write up of the night | Proof for the second pub, and for the second room |
| **v2, Phase 2 to 3** | Feb to May 2027 | The women's professional cycling calendar. Automatic Substack feed. The Cycling Planner linked | 250 followers, a named home pub, three parties run |
| **v3, Phase 3 onward** | from mid 2027 | A playbook page for a second location. Sponsor recognition | A second host in a second town |

The Canva roadmap image goes here when the slide is exported.

## Technical architecture

High level. A design document is not needed, because there is no server.

```
  A phone, from an Instagram bio link or a typed URL
        |
        v
  Static site, React and Tailwind, generated by Lovable
  Hosted free. Brand fonts self hosted from assets/fonts/
        |
        +--> Form service, free tier, over HTTPS
        |      -> email address lands in a list Joanna controls and can export
        |
        +--> Eventbrite, a link out, new tab      -> registration and reminders
        |
        +--> Substack, links out                  -> the blog
        |
        +--> Cookieless analytics                 -> page views, referrer, button clicks
```

**Where the data flows.** Out only, and to three places. Nothing is stored on the site itself. There is no database, no user accounts, no session, and no server side code, which removes most of the security surface along with most of the privacy notice.

**Why fonts are self hosted.** Loading them from Google sends every visitor's IP address to Google. Serving the two files from this repository avoids that, keeps the privacy notice to a paragraph, and is the reason no cookie banner is needed.

**The repository is the single source of brand truth.** `BRAND.md`, the logo files and the fonts live here, so the build tool is given the brand rather than asked to infer it.

## Assumptions and constraints

**Assumptions**

1. Most visitors arrive on a phone, from Instagram. Everything is designed at 390px first.
2. Eventbrite's free tier remains adequate. The event is free and there is nothing to charge for.
3. Cycling by Yoyo stays on Substack. Migrating a blog three weeks before an event is how the event does not happen.
4. A volunteer can edit the page at eleven at night, which is why every string lives in one config file.
5. The pub will be booked in time for the flyer. Everything downstream assumes this and nothing can proceed without it.

**Constraints**

| Constraint | Consequence |
| --- | --- |
| **No budget.** The domain, roughly ten pounds a year, is the only accepted cost | Free tiers only, which rules out most hosted form services' better plans |
| **Two days a week, and the site gets a quarter day** | Front loaded to w/c 16 November, then left alone |
| **One maintainer**, who is also booking the pub and hosting the night | No feature may require weekly attention |
| **Lovable's free tier is metered** | One well formed prompt and a short list of single change follow ups, not an evening of nudges |
| **The brand palette constrains the design** | Flame orange cannot be used on cream or white, which removes the obvious accent for every light section |
| **No photograph of the venue exists** | The page ships with no hero image rather than a generated one |

## Risks

| Risk | Likelihood | Impact | Mitigation |
| --- | --- | --- | --- |
| **UK broadcast rights make a legal screening impossible** | Medium | **Fatal to the event** | Ask every pub about its sports subscription before anything else. This is the first question, not a detail. Sits outside this product and nothing here can mitigate it |
| **The pub is not booked in time** | Medium | Severe. The flyer cannot print | The page is written entirely against placeholders, so it can go live and be correct without a venue, showing the email signup in place of the event |
| **The email field fails silently again** | Low | **Fatal to the product** | End to end test with an address Joanna does not own, before launch and again after the domain is connected. This is the single acceptance test |
| **Lovable produces something off brand** | Medium | Moderate, costs a day | The brand is given as files, the prohibitions are explicit, and a contrast audit is one of the six follow up prompts |
| **Lovable credits run out mid build** | Medium | Moderate | One strong first prompt. If it stops, the generated code is already in this repository and can be finished by hand |
| **Only one person can edit the site** | High | Low now, moderate in year two | Every string in one config file. A second maintainer is a Phase 2 concern, not a November one |
| **Signups do not convert to attendance** | High, it is the known base rate | Moderate | Over invite deliberately, thirty for twenty, and send the Saturday personal messages, which outperform every post |
| **A GDPR complaint about the mailing list** | Low | Moderate | Privacy notice next to the form, no data shared, one click unsubscribe. The Week 6 breach exercise is the template for what happens if it goes wrong |
| **Generated images read as photographs of the venue** | Medium | Moderate, and it is a trust risk | No hero image until there is a real photograph. The AI disclosure line on any generated image. See `assets/images/ai-generated/` |

# 5. Requirements

## User journeys

The worked example, Tuesday 8 December, the cyclo-cross explainer. Full version in `User Journey - Tuesday Cyclo-cross.md`.

**The constraint that shapes it:** Instagram captions and carousel cards are not clickable. An account gets one bio link and one story link sticker, so a post with two destinations has to use both.

| Stage | Where | Call to action | Lands on |
| --- | --- | --- | --- |
| 1 | Carousel card 5 and caption | "Link in bio" | The bio |
| 2 | Bio link | one destination | **This page** |
| 3 | Story link sticker | "Read the explainer" | The Substack article |
| 4 | **This page** | sign up, go to Eventbrite, or read the article | An email address, Eventbrite, or Substack |
| 5 | Substack closing block | "Come and watch it with us" | **This page**, then Eventbrite |
| 6 | Eventbrite | register | Confirmation and a reminder |

**The second journey, the gatekeeper.** Poster or conversation, to the URL, to the footer, to a contact address. Never signs up, and the page has to survive the visit.

**The third journey, the person who cannot come.** Arrives, reads, finds the date does not work, and leaves an email address instead of vanishing. This is the journey the current page serves worst, because it does not exist at all.

## Functional requirements

**P0.1 Hero with the next event.** Logo, the tagline, and the next watch party as date, venue and time, with a primary signup button. On a 390px phone all four must be visible without scrolling. If no event is scheduled, it shows "Next date coming soon" with the email signup in place of the button, never an empty block or a date that has passed.

**P0.2 Email capture that works.**
- Given a visitor who has never been to the site
- When they enter a valid address and submit
- Then they see confirmation on the page within two seconds, and the address appears in the list within five minutes
- A visible label, not a placeholder doing a label's job
- An invalid address shows plain language error text next to the field, not an alert box
- A double submission creates neither a duplicate nor a crash
- **Tested end to end with an address Joanna does not own.** This is the single test that protects the launch

**P0.3 What this is, in two sentences.** Plain English, no mission statement.

**P0.4 The reassurance block.** Before any cycling content. Four statements, each with room around it: it is free, no cycling knowledge needed, you do not need to bring anyone, nobody is in lycra. Then one paragraph on what the first five minutes look like.

**P0.5 Eventbrite link.** Clearly labelled with where it goes rather than "click here", opening in a new tab.

**P0.6 Substack block.** The three most recent posts, title and date, plus a link to the publication. Manual for v1. Three weeks before an event is the wrong time to debug an RSS feed.

**P0.7 Privacy notice.** What the address is used for, that it is shared with nobody, and how to unsubscribe. A visible link beside the form.

**P0.8 Favicon and social share image.** Converted from `assets/logo/roadside-collective-profile-picture.svg`. Converting is allowed, redesigning is not. Without a share image the link looks broken the moment anyone posts it.

**P0.9 Analytics.** Page views, referrer, and signup button clicks. Cookieless.

**P0.10 One config file.** Every string and every event detail in one commented file, so changing the venue is a single edit.

**P1.1** The women's professional cycling calendar, next six to eight races with dates and whether Roadside Collective is watching. The most distinctive thing on the site and the biggest time sink. First to wait if the week slips.
**P1.2** Custom domain, `roadsidecollective.co.uk`. Register and connect are two jobs and DNS can take a day.
**P1.3** A photograph of the real room, once the pub is confirmed.
**P1.4** A contact route for gatekeepers, separate from the signup.

**P2.** Brighton community cycling events calendar. Automatic Substack feed. Past events with photographs. A second location page.

**Why the P0 order is not the RICE order.** P0 runs in dependency and page order, because a build has to be sequenced. RICE decided what is in the list, not what gets built first.

## Non-functional requirements

| Area | Requirement |
| --- | --- |
| **Accessibility** | WCAG 2.1 AA. Alt text on every image. Keyboard reachable controls with visible focus. Headings in order, one h1. Body text at least 16px on mobile. **Flame orange never on cream or white, 2.65:1, fails** |
| **Performance** | Readable before the images arrive, on a slow connection on the seafront. Self hosted fonts, no render blocking third party scripts |
| **Mobile** | Verified on a real phone, not a desktop browser at a narrow width |
| **Security** | HTTPS. No user data stored on the site. No accounts, no sessions, no server side code |
| **Privacy** | Cookieless analytics, which removes the need for a cookie banner. Fonts self hosted, so no visitor IP goes to Google |
| **Maintainability** | One config file. A volunteer can change the venue at eleven at night without touching a component |
| **Reliability** | A static page on free hosting. The form service is the only runtime dependency, and its failure must be visible to the user rather than silent |
| **Brand** | The palette, type and logo rules in `BRAND.md` are requirements, not preferences |

## AI and data requirements

**No training data, no model, no inference.** This section is about the data the product handles, which is deliberately almost none.

| Data | Source | Where it lives | Retention |
| --- | --- | --- | --- |
| Email address | Typed by the visitor | The form service, then the mailing list | Until unsubscribe, reviewed annually |
| Page views, referrer, clicks | Cookieless analytics | The analytics provider, aggregated | Provider default, no individual tracking |
| Event details | The config file | This repository | Current event only |
| Registrant names | Eventbrite | Eventbrite, then the door app | Per event |
| Attendance | The Base44 door app, on the night | The door app, exportable | Per event |

**Collection principles**, carried from the Week 2 data strategy and the Week 5 GDPR work:

1. **Collect the minimum.** An email address and nothing else. No name, no phone number, no address.
2. **One source of truth per fact.** The site does not keep its own copy of the mailing list.
3. **Lawful basis is consent**, given by submitting the form, with the purpose stated beside it and one click unsubscribe on every email.
4. **The door app records attendance, never contact details**, which is a deliberate schema decision so it cannot become a second copy of the list.

**The data gap this product does not close.** Someone who sees a bike shop poster and types the URL arrives as direct traffic, indistinguishable from an Instagram tap. Poster attribution is accepted as unanswerable in v1, and going from no answer to a rough answer is the win.

# 6. Challenges

**Will there be enough data?** For analytics, yes, and it will be small. Forty addresses by 14 December is the target and twenty people in a room is the event. **These numbers are too small for anything statistical**, and that is worth saying plainly rather than dressing up a sample of twenty as a result. Conclusions in December will be anecdotes with numbers attached. They are still the right numbers, because they are the ones that decide whether there is a second party.

**How will it be acquired?** Instagram, the Substack article, posters in at least four bike shops, the Neighbourhood Gravel post, and the Saturday personal messages, which outperform everything else and are the easiest thing to skip.

**Are there enough funds?** The budget is about ten pounds a year for a domain. Every other dependency is on a free tier, which is a real risk rather than a clever saving: Lovable is metered, and a free form service can change its terms. Mitigation is that the generated code lives in this repository, so nothing is locked inside a tool.

**Is there enough user conviction?** **No, and this is the honest weak point of the whole document.** The hypothesis that social reassurance beats information comes from repeated anecdotal evidence, people saying "I would not know what I was looking at" and "I would not know anyone", and not from research. Nobody has tested the page with a stranger.

The mitigation is cheap and it is in the timeline: **two people who are not involved try the page on 24 November and say what is confusing.** Two users is not research, but it is the difference between an untested assumption and a lightly tested one, and it costs an afternoon. The real test is 13 December, when fifteen strangers either walk in or they do not.

# 7. Positioning

| Use case | Pain point | Possible solutions | Impact of solution |
| --- | --- | --- | --- |
| Decide whether this is for someone like me | Nothing anywhere answers it, and it is the objection that costs the most attendance | The reassurance block, the first five minutes paragraph, a photograph of the real room | **Highest. It is the hypothesis the product exists to test** |
| Find the date, venue and time | Buried in Instagram posts that scroll away, no stable address for a poster | Hero with the next event, one short URL on every printed asset | High. Unblocks the flyer and the bike shop round |
| Register for the event | The live page has a signup button and no email field, so everyone fails silently | Working email capture, plus a labelled Eventbrite link | **Fatal if unsolved. Every other effort is wasted without it** |
| Stay in touch when the date does not work | No mechanism at all, so the person is lost permanently | Email capture that is useful on its own, not just a route to Eventbrite | High, and it compounds. The cheapest person to reach next time |
| Check this is a real organisation | One sparse Instagram account, no site, no contact address | A page of its own, a purpose, a contact route for gatekeepers | Moderate for numbers, **high for getting a venue at all** |
| Follow women's racing | Substack exists and nothing links to it where a stranger lands | The three most recent posts, featured | Moderate. Proves the project produces something |

# 8. Measuring success

## Metrics

**Leading, read within a week of launch.**

| Metric | Success | Stretch | Where |
| --- | --- | --- | --- |
| Signup conversion, visits to email submissions | 15% | 25% | Analytics and the list count |
| Phone bounce rate | under 60% | under 45% | Analytics |
| Eventbrite clickthrough from the site | 20% of visitors | 30% | Eventbrite referrer |
| Form errors per 100 submissions | under 5 | 0 | Manual check of the list |
| Time to find date, venue and time | one screen, no scroll | same | Tested by hand on a 390px phone |

**Lagging, read after 13 December.**

| Metric | Target | Where |
| --- | --- | --- |
| Email list by 14 December | 40 addresses | The list |
| Eventbrite signups by Saturday night | 30 | Eventbrite |
| Through the door on the day | 20 | The door app |
| Attendees who say the website is how they found it | 5 | Ask them on the night |
| Visits attributable to the bike shop posters | any measurable number at all | Analytics referrer, and direct traffic in the shop round week |

The last one is deliberately vague, because it is the question that currently has no answer at all. Going from no answer to a rough answer is the win.

## AI specific metrics

No model ships, so there is no precision, recall or drift to report, and inventing one would be dishonest. What is measurable is the quality of the AI assisted **production**, and that is worth measuring because it is where the course learning sits.

| What | Definition of quality | Good enough to ship |
| --- | --- | --- |
| **The generated build** | Passes a fixed checklist: no orange on cream or white, no invented venue or URL, no stock hero photograph, email field present, reassurance block above the cycling content, every string in the config file | **Six of six.** Any failure is a follow up prompt, not a manual patch, so the prompt improves rather than the symptom |
| **Accessibility of the generated output** | WCAG 2.1 AA on every text pair, keyboard focus visible, headings in order | Zero AA failures. Not negotiable, because it is a brand rule here |
| **The content pipeline** | Factual accuracy of AI assisted copy. No invented statistic, result or rider record | **Zero invented facts.** Every claim checkable, which is why the explainer names no rider |
| **Prompt efficiency** | Builds reaching an acceptable page within the free credit allowance | One main prompt plus at most six single change follow ups |

**The judgement that matters more than any of these:** whether a model belongs in front of users at all. The answer for v1 is no, with the three conditions for revisiting it written down in section 4 so it is a decision with criteria rather than an oversight.

## North Star metric

> **Strangers through the door, per watch party.**
> People who attend and are not personal friends of the organiser.

**Why this one.** It is the only number that cannot be faked by effort and cannot be flattered by a vanity metric. Followers, subscribers and even signups can all rise while the room stays empty and full of friends. If fifteen people who were not asked personally turn up, the proposition works and it will scale to a second pub and a second town. If they do not, nothing else on this page matters.

It is also the number that convinces the next landlord, which is the actual constraint on the project.

**It is measured by the Base44 door check in app**, which has a `source` field separating Eventbrite registrants from walk ins and a `first_timer` flag. Without that app this metric would be a guess made the next morning, which is exactly what it was before.

**Target: 15 of 20 on 13 December 2026.**

# 9. Launching

## Stakeholders and communication

| Stakeholder | Interest | How they are kept informed |
| --- | --- | --- |
| **Joanna** | Owner, builder, host | This document, and the Notion tracker |
| **Lucas, tutor** | The site is the agreed Project Week piece | Reviewed in the Week 8 submission. The build counts twice |
| **The pub landlord** | Needs to know numbers, and that this is real | Direct contact. The site is what they check first |
| **Neighbourhood Gravel members** | The warm contacts who fill the first room | A group post, then **individual messages on the Saturday**, which outperform every post in the plan put together |
| **Bike shops** | Hosting posters, potential Phase 3 sponsors | The shop round, w/c 23 November. The site gives them something to check |
| **Email subscribers** | Want to hear about the next one | Substack, one post a week |
| **Attendees** | Want the details, and want to be asked back | Eventbrite confirmation and reminder, then the Monday 14 December post |

## Roll-out strategy

Sequential, and the dependencies are unforgiving. One slip at the top moves everything.

| Date | Milestone | Blocks |
| --- | --- | --- |
| Fri 13 Nov | **Email field added to the Mailchimp page as a stopgap** | Every signup until the real site exists. Twenty minutes, highest value job on the list |
| Sat 14 Nov | Platform, name and domain decided and registered | The build, and the Instagram handle |
| Tue 17 Nov | Copy written | The build |
| Wed 18 Nov | Images chosen, or the decision taken to ship without a hero | The build |
| **Sun 22 Nov** | **Site live, domain connected, share image and favicon in place** | The flyer, which carries the address |
| Mon 23 Nov | Accessibility pass, phone check, **end to end signup test** | Whether any of it works |
| Tue 24 Nov | Two uninvolved people try it and say what is confusing | Last chance to change anything |
| Sat 28 Nov | Flyer printed, bike shop round | **Nothing after this can change the URL** |
| w/c 30 Nov | Push week. Substack preview, daily Instagram, personal asks | 30 signups |
| Sun 13 Dec | The first watch party | The North Star reading |
| Mon 14 Dec | Photographs posted, next date announced if there is one | The second party, and the second pub |

**Go to market is not a launch announcement.** The site is infrastructure for a seven day content push and a bike shop round, not an event in itself. Nobody is told the website is live. They are told there is a watch party, and the website is how they check.

**If the week slips**, the P1 calendar waits. Never the pub, and never P0.2.

---

## Appendix: what carried over from the earlier PRD

The previous requirements document, `Roadside Collective/Launch Campaign/Website PRD.md`, was written to a different template and is superseded. Checked after this was drafted, to make sure nothing material was lost in the rewrite.

**Carried across:** all eleven P0 requirements, the three personas, the user stories including the edge cases, the WCAG pass, both metrics tables, the timeline and its dependencies, and the rule that the calendar is what waits.

**Deliberately changed:**

| Earlier PRD | This one | Why |
| --- | --- | --- |
| Platform "still open, and it blocks the build" | Lovable, decided | The open question is answered |
| Recommendation: hand built HTML | Lovable generates an editable codebase | Same control, a week less work, and it is the AI learning the project is for |
| P1.3 "a photograph of a real room" | Unchanged, plus an explicit rule that **no hero image ships until it exists** | Generated pub images exist and using one above a date and a venue would be a claim about a real place |
| Open question: "is cycling going into the brand name" | Still open, still blocking the domain | Not this document's to settle |

**Not carried across, deliberately:** the four option platform comparison table, which was decision making rather than requirements, and is preserved in the earlier file.
