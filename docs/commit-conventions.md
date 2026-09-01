# Commit-Konventionen

Dieses Repo erzwingt **[Conventional Commits](https://www.conventionalcommits.org/)**. Damit lassen sich später
automatisiert Versionen und Changelogs erzeugen (semantic-release).

## Einmalige Einrichtung

Die Git-Hooks werden von [Husky](https://typicode.github.io/husky/) verwaltet und aktivieren sich erst nach:

```bash
npm install
```

Danach prüft der `commit-msg`-Hook jede Commit-Message lokal. Ein zusätzlicher GitHub-Actions-Workflow
(`.github/workflows/commitlint.yml`) prüft alle Commits eines Pull Requests noch einmal – auch wenn jemand die
lokalen Hooks umgeht (`git commit --no-verify`) oder `npm install` nicht ausgeführt hat.

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

| Commit | Release |
| --- | --- |
| `fix: …` | Patch (0.0.**x**) |
| `feat: …` | Minor (0.**x**.0) |
| `feat!: …` oder Footer `BREAKING CHANGE:` | Major (**x**.0.0) |
| `docs:`, `chore:`, `ci:`, `test:`, `refactor:`, `style:` | kein Release |

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
