# Interactive Come Follow Me Lesson

A youth Sunday School lesson built as a click-through **TV presentation**. Everything (content, styling, animations, games, scoring) lives in `public/index.html`; the only outside request is two Google Fonts (Cormorant Garamond and Inter), and it falls back to system fonts offline. Plug a laptop into the TV, open the site, press **F** for full screen, and click through together.

**Current lesson:** October 26 – November 1, 2026 · "I Will Turn Their Mourning into Joy" · Jeremiah 31–33; 36–39; Lamentations 1; 3
([official lesson](https://www.churchofjesuschrist.org/study/manual/come-follow-me-for-home-and-church-old-testament-2026/44?lang=eng)).

## What's in the deck

The background moves from night to sunrise to full day as the lesson goes from mourning to joy. The look is deliberately understated: serif type, gold line-art icons, and quiet animations.

| Slides | Section | What happens |
| --- | --- | --- |
| 1–4 | Intro | Title, "worst day turned around" warm-up, Jeremiah trading card that flips, animated map of Babylon marching on Jerusalem (plus the Lehi / 1 Nephi 7:14 tie-in) |
| 5–7 | Story 1 · Jeremiah 36 | The scroll is written, cut up and burned, then rewritten with "many like words"; discussion |
| 8–10 | Story 2 · Jeremiah 37–39 | Jeremiah sinks in the pit; guess what Ebed-melech brought; the class pulls him out five heaves at a time; "old rags" kindness ideas |
| 11–14 | Story 3 · Jeremiah 39; Lamentations 1; 3 | Jerusalem falls, Lamentations' sad songs, then the sunrise of "new every morning" |
| 15–16 | Story 4 · Jeremiah 32 | "Would you buy it?" hand-vote, then the deed drops into the clay jar |
| 17–21 | Jeremiah 31; 33 | Law flies from stone into a heart; "Stone or Heart?" sorting game; everlasting love; "Call unto me"; the Branch grows from a stump |
| 22–29 | Lightning round | Six team quiz questions with a 20-second timer, scoreboard, and winner reveal |
| 30–32 | Wrap-up | Mourning → Joy flip-tile recap, pick-one challenge, Jeremiah 31:13 finale |

## Controls

| Key | Action |
| --- | --- |
| → · Space · Page Down · click | Next (reveals the next part of a slide first) |
| ← · Page Up · click the left edge | Back |
| N | Teacher notes for the current slide (visible on the TV too) |
| S | Show or hide the team scoreboard (it shows automatically during the quiz) |
| B or . | Black screen |
| F | Fullscreen |
| M | Sound on/off |
| ? | Help |

Most presentation clickers send Page Up/Page Down and work as-is. Quiz answers, the PULL button, votes, recap tiles and challenge cards can also be clicked. Your slide and team scores survive a refresh (kept in the browser tab only).

## Teacher script

`public/notes.html` (served at `/notes.html`) is a slide-by-slide script: what to say, when to click, pauses, questions with likely answers, a time budget per slide, and which parts to cut for a shorter class. It works on a phone and prints cleanly. The deck's help screen (press **?**) links to it.

## Past lessons

Earlier lessons are kept in `public/archive/` (for example `/archive/2026-10-05-isaiah-50-57.html`).

## Weekly update

1. Move the current `public/index.html` into `public/archive/`.
2. Edit the slides in `public/index.html`: each `<section class="slide">` is one slide, `data-step="n"` makes an element appear on the nth click, `data-mood` sets the sky (night, dusk, dawn, day), and `<aside class="notes">` holds the teacher notes.
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
