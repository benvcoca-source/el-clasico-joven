# El Clásico Joven

Rivalry scoreboard for Luis & Jorge vs Ben & Fabio. One self-contained page
(`index.html`) with no build step and nothing to install.

Live site: https://benvcoca-source.github.io/el-clasico-joven/

## Logging a session
Open `index.html` and find the `DATA` block near the bottom. Add one object to
`sessions` after each Clásico:

```js
sessions: [
  { id: 1, label: "Opening Clásico", date: null, matchesA: 2, matchesB: 1 },
  { id: 2, label: "Jornada 2", date: "2026-11-25", matchesA: 0, matchesB: 0 }
],
```

`matchesA` is Luis & Jorge, `matchesB` is Ben & Fabio. Scores, streaks, the
beer tab (the losing pair buys), the record and the match log all update from
that one list.

## Locking the next date
Once the group has voted on WhatsApp, set the date in `nextMatch`:

```js
nextMatch: { options: ["2026-11-18", "2026-11-25"], confirmed: "2026-11-25", time: "19:00" }
```

Leave `time: null` if the kickoff time is not set yet. The "Next Clásico"
section then turns into a live countdown.

## Hosting
GitHub Pages, deployed from the `main` branch, root folder. Edits to
`index.html` go live within a minute or two.
