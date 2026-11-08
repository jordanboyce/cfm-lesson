# Interactive Come Follow Me Lesson

A youth Sunday School lesson built as a click-through **TV presentation**. Everything (content, styling, animations) lives in `public/index.html`; the only outside request is two Google Fonts (Cormorant Garamond and Inter), and it falls back to system fonts offline. Plug a laptop into the TV, open the site, press **F** for full screen, and click through together.

**Current lesson:** November 9–15, 2026 · "There Is No Other God That Can Deliver" · Daniel 1–7
([official lesson](https://www.churchofjesuschrist.org/study/manual/come-follow-me-for-home-and-church-old-testament-2026/46?lang=eng)).

## What's in the deck

Ordinary slides with builds and animations, no games, scoring or sound this week. One quiet dark background, serif type, gold line icons, and a plain fade between slides. The wording is kept simple for teenagers: every hard King James verse has an "In plain words" line under it, and each story has an everyday example (the party, tryouts, brushing your teeth). Each scene animates as you click: the name cards flip, the ten-day test counts up, the statue builds and shatters, the crowd bows while three stand, the fourth figure appears in the flames, the writing appears on the wall, and the lions' den opens to the morning.

| Slides | Section | What happens |
| --- | --- | --- |
| 1–3 | Intro | Title with the Babylon skyline, "the only one in the room" warm-up, map of the captives' road and the four names flipping to their Babylonian names |
| 4–5 | Story 1 · Daniel 1 | "Purposed in his heart": the king's table versus pulse and water, the ten-day test, decide before the moment comes |
| 6–8 | Story 2 · Daniel 2 | The statue builds metal by metal, the stone cut without hands shatters it and fills the earth; D&C 65:2, the stone is still rolling |
| 9–11 | Story 3 · Daniel 3 | The music plays and the crowd bows while three stand; "but if not"; the furnace and the fourth man; "no other God that can deliver" |
| 12 | Daniel 4–5 | Two proud kings: the tree cut to a stump, and the writing on the wall |
| 13–14 | Story 4 · Daniel 6 | Daniel at eighty prays "as he did aforetime"; the den seals, lions' eyes glow, and morning comes |
| 15 | Daniel 7 | The Son of man comes with the clouds; the Ancient of days; Christ's kingdom never falls |
| 16–18 | Wrap-up | "In short" six-point summary, pick-one challenge, "but if not" finale |

The deck is built for a 25-minute class: 18 slides, about 23½ minutes at the pace in the teacher script. If time runs out, press **W** (or the **Wrap up** button) from any slide to jump to the "In short" slide; the script has a 2-minute summary to read aloud there.

## Controls

| Key | Action |
| --- | --- |
| → · Space · Page Down · click | Next (reveals the next part of a slide first) |
| ← · Page Up · click the left edge | Back |
| N | Teacher notes for the current slide (visible on the TV too) |
| B or . | Black screen |
| F | Fullscreen |
| W | Out of time: jump to the "In short" summary |
| ? | Help |

Most presentation clickers send Page Up/Page Down and work as-is. The challenge cards on the last slides can be clicked. Your place in the deck survives a refresh (kept in the browser tab only).

## Teacher script

`public/notes.html` (served at `/notes.html`) is a slide-by-slide script: a five-minute prep box with who's who and pronunciations, what to say, when to click, pauses, questions with likely answers, a time budget per slide that fits a 25-minute class, what to cut if you run behind, a 2-minute wrap-up to read aloud, and answers to questions the class may ask. It works on a phone and prints cleanly. The deck's help screen (press **?**) links to it.

## Past lessons

Earlier lessons are kept in `public/archive/` (for example `/archive/2026-10-26-jeremiah-31-39.html`, with its script at `/archive/2026-10-26-jeremiah-31-39-notes.html`).

## Weekly update

1. Move the current `public/index.html` and `public/notes.html` into `public/archive/`.
2. Edit the slides in `public/index.html`: each `<section class="slide">` is one slide, `data-step="n"` makes an element appear on the nth click, `data-steps="n"` sets how many clicks a slide has when the builds are CSS-only (`.s1`, `.s2`, … classes are added to the slide), and `<aside class="notes">` holds the teacher notes.
3. Open `public/index.html` locally in a full-screen browser window and click through every slide.
4. Deploy:

```bash
firebase deploy --only hosting
```

Pushes to `master` also deploy through the GitHub Actions workflow in `.github/workflows`.

## First Firebase setup

```bash
firebase login
firebase use --add
firebase deploy --only hosting
```
