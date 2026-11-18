# 🧠 MindMath Quest

**Five minutes of mental math that feels like a game — and actually teaches you something.**

MindMath Quest is a free, offline-first, single-page browser trainer. It detects which mental-math techniques need work, demonstrates a shortcut, and then revisits the concept until you can solve it independently. Daily quests, XP, ranks, combos, and collectible trophies keep practice interesting without turning it into a second job.

[**▶ Play MindMath Quest**](https://zaqxen.github.io/mindmath-adaptive-coach/) · [View source](https://github.com/zaqxen/mindmath-adaptive-coach)

> **Hosting note:** The Play link becomes live after GitHub Pages is enabled for this repository. See [Publish on GitHub Pages](#publish-on-github-pages).

## Why it works differently

- **Five minutes or 12 questions per day**, whichever happens first. Leave early if you want; the timer pauses when you switch tabs.
- **15 techniques across five areas:** addition, subtraction, multiplication, division, and percentages.
- **Personalized weak-spot detection:** incorrect answers, repeated hints, and slow independent solutions inform what to practice next.
- **Step-by-step, then solo:** see a worked method after a mistake, get similar questions, and gradually lose the training wheels as you improve.
- **Eight separate math levels per area:** promotion requires sustained accurate *independent* performance; a level may drop when your fundamentals need review.
- **Game progress:** receive small XP rewards for practice and a bigger reward for independent correct answers. Complete one approachable daily quest, build correct-answer combos, unlock 12 trophies, and climb eight *player* ranks.
- **Gentle by design:** no ads, payments, login, cloud analytics, endless feeds, or penalties for taking days off. Earned trophies are permanent.

### A tiny session

1. Open the page. You'll see your suggested focus and today's micro-quest.
2. Hit **Start today's session**.
3. Calculate mentally. Use **Show a technique** or reveal steps whenever you need help.
4. Review the answer and try another. The game records whether a correct answer needed guidance.
5. After five minutes or twelve answers, get a short summary, XP, and any earned trophies.

Accuracy and understanding matter more than speed. **XP never controls your math difficulty**; the adaptive learning model does.

## Game mechanics at a glance

| Mechanic | How it works |
| --- | --- |
| XP | Correct independent answers earn more than guided answers; incorrect attempts get a tiny effort point; a level-up earns a one-off bonus. |
| Daily quest | One small goal based on your needs, or a rotating general challenge. Complete it once for bonus XP. |
| Combo | Consecutive correct answers earn a modest bonus. A miss resets only the current combo. |
| Player ranks | Eight milestones based on accumulated XP; these are **not** math levels. |
| Trophy cabinet | Twelve achievements for showing up, practicing independently, using guidance, exploring skills and increasing mastery. |
| Skill levels | Separately tracked for addition, subtraction, multiplication, division and percentages, with promotion/demotion backed by recent evidence. |
| Consistency | Practice-day counters and streaks are shown, but missed days **do not** remove points, rank, or trophies. |

**Difficulty rules:** Promotion requires at least 9/10 recent correct answers in a skill, at least 8 unaided correct answers, reasonable solving time, variety across techniques, and no detected weak technique in that skill. After ten recent answers at the current level, 5 or fewer correct leads to a gentler level. One wrong answer cannot demote you.

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

Issues, bug fixes, lesson improvements and accessible design suggestions are welcome. Please keep the core promise intact: **short sessions, learning before speed, privacy by default, no mandatory signup, and no manipulative engagement loops**.

The app is deliberately one file:

```text
index.html   Complete application: markup, styles, learning logic, game systems
README.md    Documentation and publishing steps
```

To test a change, open the page in a browser, complete a short session, check that the daily cap works, then verify `localStorage` survives a refresh. The inline JavaScript can also be extracted from `index.html` and checked with `node --check`. Review older backup imports when changing the save format.

**License:** No explicit software license has been selected yet. Please contact the repository owner before redistributing or incorporating the source into another product. You are welcome to open issues or propose changes through GitHub.