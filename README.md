# Angular Workshop – Lessons

Dieses Repository enthält **nur die Lessons** (Aufgabentexte, Hinweise, Metadaten) für den Angular-Workshop.
Der Übungscode liegt in [`workshops-de/angular-workshop`](https://github.com/workshops-de/angular-workshop),
die Folien in Google Slides.

## Für wen

Für Trainer:innen, die Aufgaben anlegen oder anpassen. Lernende sehen die Inhalte über die
Workshop-Plattform, nicht über dieses Repo.

## Einrichtung (einmalig)

```sh
npm install                     # aktiviert den commit-msg-Hook (Husky + commitlint)
git submodule update --init     # holt die Beispiellösungen nach ./sample-solution
```

Node-Version: siehe [.node-version](./.node-version) (via `fnm`/`nvm`/`nodenv` automatisch).

## Aufbau

```
lessons/<NN-slug>/
  lesson.yml                    # Titel, Position, Trainer, Slides-ID …
  tasks/<NN-slug>/
    task.yml                    # Titel, Position, Kategorie, Zeitschätzung, git_tag_completed
    body.md                     # Aufgabenstellung (Pflicht)
    hint.md                     # optionaler Hinweis
    bonus.md                    # optionale Zusatzaufgabe
```

Reihenfolge steuert das `position`-Feld (10, 20, 30 … – Lücken lassen für spätere Einschübe).
Details und Konventionen zum Anlegen: [docs/lessons.md](./docs/lessons.md) bzw. [CLAUDE.md](./CLAUDE.md).

## Ändern & veröffentlichen

1. Branch anlegen, Aufgabe in `lessons/…` bearbeiten.
2. Committen im **Conventional-Commits**-Format – der Hook lehnt ungültige Messages ab.
   Beispiele und Release-Wirkung: [docs/commit-conventions.md](./docs/commit-conventions.md).
   - `feat: …` → Minor, `fix: …` → Patch, `docs:`/`chore:`/`refactor:` → kein Release.
3. PR gegen `main`. CI ([.github/workflows/ci.yml](./.github/workflows/ci.yml)) prüft die Commit-Messages.
4. Nach dem Merge erzeugt **semantic-release** automatisch die neue Version, aktualisiert
   [CHANGELOG.md](./CHANGELOG.md) und legt ein GitHub Release an. So sehen andere Trainer:innen auf einen
   Blick, was sich an Aufgaben und Beschreibungen geändert hat (Repo „Watch" → Benachrichtigung).

## Folien

Slides liegen in Google Slides und sind über mehrere Präsentationen verteilt (`google_slide_id` in der
jeweiligen `lesson.yml`). Vor Änderungen die Skill-Anleitung unter
[.claude/skills/google-slides-workshop-teacher](./.claude/skills/google-slides-workshop-teacher/SKILL.md)
lesen.

## Beispiellösungen

Das Submodul [`sample-solution/`](./sample-solution) zeigt auf `workshops-de/angular-workshop`. Jeder Commit
dort ist die Lösung zu einer Aufgabe; das passende Tag steht in `task.yml` unter `git_tag_completed`.
