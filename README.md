# Interactive Come Follow Me Lesson

This is a dependency-free static site. All lesson content, styling, and behavior are contained in `public/index.html`.

## Weekly update

1. Edit the page title, scripture references, questions, scenarios, answers, and official lesson link in `public/index.html`.
2. Open `public/index.html` locally in a browser and test every reveal and navigation button.
3. Deploy from this directory:

```bash
firebase deploy --only hosting
```

## First Firebase setup

If this directory is not associated with a Firebase project yet, run:

```bash
firebase login
firebase use --add
firebase deploy --only hosting
```

The commitment text box is browser-only. It does not save or transmit what a student types.
