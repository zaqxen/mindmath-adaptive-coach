# 🧠 MindMath Quest

**Five minutes of mental math that feels like a game — and actually teaches you something.**

MindMath Quest is a free, offline-first, single-page browser trainer. It detects which mental-math techniques need work, demonstrates a shortcut, and then revisits the concept until you can solve it independently. Daily quests, XP, ranks, combos, and collectible trophies keep practice interesting without turning it into a second job.

[**▶ Play MindMath Quest**](https://zaqxen.github.io/mindmath-adaptive-coach/) · [View source](https://github.com/zaqxen/mindmath-adaptive-coach)

> **Hosting note:** The Play link becomes live after GitHub Pages is enabled for this repository. See [Publish on GitHub Pages](#publish-on-github-pages).

## Why it works differently

- **Five minutes or 12 questions per day**, whichever happens first. The timer only runs while a question is visible for solving. You can end early.
- **15 techniques across five areas:** addition, subtraction, multiplication, division, and percentages.
- **Personalized weak-spot detection:** incorrect answers, repeated hints, and slow independent solutions inform what to practice next.
- **Step-by-step, then solo:** see a worked method after a mistake, get similar questions, and gradually lose the training wheels as you improve.
- **Adaptive digit bands:** each operation moves up or down through one- to five-digit problems based on independent solving performance.
- **Game progress:** receive small XP rewards for practice and a bigger reward for independent correct answers. Complete one approachable daily quest, build correct-answer combos, unlock 11 trophies. An optional assessment estimates your starting Rank. Daily practice updates it.
- **Gentle by design:** no ads, payments, login, cloud analytics, endless feeds, or penalties for taking days off. Earned trophies are permanent.

### A tiny session

1. Open the page. You'll see your suggested focus and today's micro-quest.
2. Hit **Start today's session**.
3. Press **Ready** to reveal a question and start its timer. Use **Show a technique** when you need help.
4. Press **Solved it** when you know the answer, then type it. Review the result and use **Next** to get ready for another question.
5. After five minutes or twelve answers, get a short summary, XP, and any earned trophies.

Rank combines correct answers and solving speed. **XP never controls Rank or math difficulty**. The assessment estimates starting difficulty per operation. Independent solves in daily practice update both Rank and question difficulty.

## Game mechanics at a glance

| Mechanic | How it works |
| --- | --- |
| XP | Correct independent answers earn more than guided answers; incorrect attempts get a tiny effort point; advancing a digit band earns a one-off bonus. |
| Daily quest | One small goal based on your needs, or a rotating general challenge. Complete it once for bonus XP. |
| Combo | Consecutive correct answers earn a modest bonus. A miss resets only the current combo. |
| Rank | Twenty motivational titles from Foundations through 1st Grader to Genius, based on the assessment baseline and recent independent practice. |
| Trophy cabinet | Eleven achievements for showing up, practicing independently, using guidance, exploring skills and increasing mastery. |
| Operation ranks | Addition, subtraction, multiplication, division and percentages each show a Rank. Each operation adapts independently. |
| Own pace | No day streak or accuracy percentage. Missed days do not remove points, rank, or trophies. |

## Rank assessment and charts

Use **Practice and assessment settings** to choose the operations and the largest operand, from one to five digits. For percentages the limit applies to the base amount. Both activities honor the same settings. Rank averages the enabled operations, and each digit band adds up to 20 points, so one-digit work tops out at 20 and three-digit work at 60. Settings can change between sessions.

**Take speed test** gives two questions per selected operation and digit band as an initial estimate. In both activities, **Ready** reveals the question and **Solved it** stops the timer before entry. Reading and button reaction are included. A tab switch during solving discards the practice question or cancels the assessment. Previous completed practice answers stay saved.

A correct answer earns `100 × min(1, targetSeconds / max(2, solveSeconds))` timing points. Incorrect answers earn zero. App-defined full-score targets in seconds for 1/2/3/4/5 digits are:

| Operation | Targets | Question format |
| --- | --- | --- |
| Addition | 2 / 4 / 7 / 10 / 14 | Add numbers up to the selected length |
| Subtraction | 2 / 5 / 8 / 12 / 17 | Subtract numbers up to the selected length |
| Multiplication | 2 / 6 / 10 / 15 / 21 | Selected-length number times a small multiplier |
| Division | 2 / 6 / 11 / 17 / 24 | Selected-length dividend divided by one digit |
| Percentages | 2 / 5 / 8 / 12 / 17 | Find a basic percentage of the selected-length amount |

Each independent practice answer moves its band score toward the new result. A band at 85 timing points unlocks the next digit length. A difficult solve can bring back a shorter problem. Guided practice provides coaching without changing Rank. Click Rank for all 20 titles. Grade and career titles are motivational. They lack validation against real-world groups.

**My Rank & Charts** opens a dashboard with operation comparison, recent gains and drops, a digit-band grid, and a selectable Rank history for the overall score or one operation. Overall history uses the same operation selection and digit ceiling. Operation history compares checkpoints at the same digit ceiling, and records practice only when the operation received an independent answer. Older saves keep their overall history and gain operation checkpoints as new practice is completed. Changing settings preserves excluded operation data and results from longer bands. Existing backups keep their practice totals, trophies, and historical tests. The previous assessment can seed matching digit bands. Division previously counted the quotient, so new division results use the displayed dividend.

## Run it

No installation, build tools, API keys, dependencies, or account needed.

- **Online:** visit the [GitHub Pages site](https://zaqxen.github.io/mindmath-adaptive-coach/) once Pages has been enabled.
- **Offline:** download `index.html` and open it in a modern browser. Browser behavior for `file://` storage varies; see the storage note below.
- **Local development:** serve the folder and open it in your browser:

  ```bash
  python3 -m http.server 8000
  ```

  Visit <http://localhost:8000/>.

## Publish on GitHub Pages

This repository is already arranged for static hosting: **`index.html` sits in the repository root**. The owner only needs to enable publishing:

1. Open **Settings → Pages** in this repository.
2. Under **Build and deployment**, choose **Deploy from a branch**.
3. Select branch **`main`**, folder **`/(root)`**, then **Save**.
4. When GitHub reports a successful deployment, the site will be accessible at **https://zaqxen.github.io/mindmath-adaptive-coach/**.

After that, pushes to `main` update the live page automatically. No GitHub Actions workflow is needed for this static single-file app.

## Privacy, backups, and migrating progress

**Everything is stored on your own device** in the browser's `localStorage` under the key `mindmath_daily_v1`. No progress is uploaded to GitHub, and there are no analytics or third-party requests.

- Use **Export backup** to save a portable JSON backup of your progress; use **Import backup** to restore it. Import replaces current stored progress only after confirmation.
- If you previously trained using a downloaded `mental_math_daily.html`, **export from the old page and import on the GitHub Pages site**. Browser storage is scoped to the site's origin, so moving from `file://` or `localhost` to GitHub Pages cannot copy it automatically.
- Backups from the older MindMath data format are accepted. Old math skill progress is retained; older records do not pretend to have earned the new quests.
- Clearing browser storage, private browsing, or changing browser/device can remove local progress. Make a backup before switching.
- Since saved progress can be edited locally, trophies are personal motivation, **not a competitive or verified leaderboard**.

## Contributing

Issues, bug fixes, lesson improvements and accessible design suggestions are welcome. Please keep the core promise intact: **short sessions, accurate and faster solving, privacy by default, no mandatory signup, and no manipulative engagement loops**.

The app is deliberately one file:

```text
index.html   Complete application: markup, styles, learning logic, game systems
README.md    Documentation and publishing steps
```

To test a change, open the page in a browser, complete a short session, check that the daily cap works, then verify `localStorage` survives a refresh. The inline JavaScript can also be extracted from `index.html` and checked with `node --check`. Review older backup imports when changing the save format.

**License:** No explicit software license has been selected yet. Please contact the repository owner before redistributing or incorporating the source into another product. You are welcome to open issues or propose changes through GitHub.
