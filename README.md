# Interactive Come Follow Me Lesson

A gamified, dependency-free youth Sunday School lesson. Everything (content, styling, games, scoring) lives in `public/index.html`. Students open the site on their phones and the class moves through seven "quests" together.

**Current lesson:** October 5–11, 2026 · "He Hath Borne Our Griefs, and Carried Our Sorrows" · Isaiah 50–57
([official lesson](https://www.churchofjesuschrist.org/study/manual/come-follow-me-for-home-and-church-old-testament-2026/41?lang=eng)).

## What's on the page

| Quest | Lesson section | Game |
| --- | --- | --- |
| 1 Start | Introduction (captivity in Babylon, lion vs. lamb) | Poll: what kind of rescuer would you want? |
| 2 Hope | Isaiah 50–52 · The future is bright | Sort 12 verses into the manual's study chart; 5-second "put on thy strength" tap meter; scripture-help flip cards |
| 3 Lamb | Isaiah 53 · Jesus Christ took upon Himself my sins and sorrows | Movie-hero vs. Isaiah 53 flip cards; lesson videos; "we" to "I" pronoun swap; private burden chips |
| 4 Return | Isaiah 54; 57:15–19 · Jesus Christ wants me to return to Him | True/false myth-busting deck; President Uchtdorf quote reveal |
| 5 Invite | Isaiah 55–56 · Take hold of my covenant | Guest-list stamp cards; covenant checklist; "seek the Lord" hidden-card game; His higher ways quiz |
| 6 Round | Whole block | 60-second, 10-question lightning quiz with speed bonus |
| 7 Finish | Personal application | Badge gallery, rank, commitment |

Students earn XP for correct answers and a badge per quest. XP, badges and anything typed stay in the browser tab and are never sent or saved.

The **Teacher notes** link in the footer toggles discussion prompts and manual references inside each quest.

## Lesson videos

Quest 3 has cards for the videos referenced in the lesson. By default each card is a poster that opens the video on churchofjesuschrist.org. To embed a player instead, find the `videos` array in the script near the comment `Quest 3: lesson videos`, open the video in the Church media library, choose Share > Embed, and paste the iframe `src` URL into that video's `embed` field.

## Weekly update

1. Replace the lesson title, dates, scripture block, quest content, quiz bank and the official lesson link in `public/index.html`.
2. Open `public/index.html` locally in a browser and play through every quest on a phone-sized window.
3. Deploy:

```bash
firebase deploy --only hosting
```

Pushes to `main` also deploy through the GitHub Actions workflow in `.github/workflows`.

## First Firebase setup

```bash
firebase login
firebase use --add
firebase deploy --only hosting
```
