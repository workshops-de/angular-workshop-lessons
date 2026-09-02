# Commit-Konventionen

Dieses Repo erzwingt **[Conventional Commits](https://www.conventionalcommits.org/)**. Damit lassen sich später
automatisiert Versionen und Changelogs erzeugen (semantic-release).

## Einmalige Einrichtung

Die Git-Hooks werden von [Husky](https://typicode.github.io/husky/) verwaltet und aktivieren sich erst nach:

```bash
npm install
```

Danach prüft der `commit-msg`-Hook jede Commit-Message lokal. Der GitHub-Actions-Workflow
(`.github/workflows/ci.yml`, Job `commitlint`) prüft alle Commits eines Pull Requests noch einmal – auch wenn
jemand die lokalen Hooks umgeht (`git commit --no-verify`) oder `npm install` nicht ausgeführt hat.

## Format

```
<type>(<scope>): <subject>

<body>

<footer>
```

- **type** (Pflicht): `feat`, `fix`, `docs`, `style`, `refactor`, `perf`, `test`, `build`, `ci`, `chore`, `revert`
- **scope** (optional): betroffener Bereich, z. B. der Lesson-Ordner (`04-angular-components`)
- **subject** (Pflicht): kurz, klein geschrieben, kein Punkt am Ende, Imperativ

## Auswirkung auf Releases

Bei jedem Push/Merge auf `main` läuft `.github/workflows/ci.yml` (Job `release`, nach bestandenem
`commitlint`) mit [semantic-release](https://semantic-release.gitbook.io/). Es liest die Conventional Commits seit dem letzten
Tag, berechnet die nächste Version, aktualisiert [CHANGELOG.md](../CHANGELOG.md), setzt einen Git-Tag
(`vX.Y.Z`) und legt ein GitHub Release an. Andere Trainer werden über die Releases-Seite (Watch) informiert.
Die Historie startet bei der Baseline **`v2.0.0`**.

| Commit | Release |
| --- | --- |
| `fix: …` | Patch (2.0.**x**) |
| `feat: …` | Minor (2.**x**.0) |
| `feat!: …` oder Footer `BREAKING CHANGE:` | Major (**x**.0.0) |
| `docs:`, `chore:`, `ci:`, `test:`, `refactor:`, `style:` | kein Release |

Der Release-Commit von semantic-release (`chore(release): … [skip ci]`) triggert dank `[skip ci]` keinen
weiteren Lauf.

## Beispiele

```
feat(06-angular-signal-forms): add task for cross-field validation
fix(05-angular-routing): correct route guard example
docs: clarify lesson authoring workflow
chore: bump commitlint config
```

Ungültig (wird abgelehnt):

```
Use signal
Update lesson
WIP
```

## Bestehende Historie

Ältere Commits werden **nicht** umgeschrieben. Die Regel gilt ab Einführung des Guards für neue Commits.
