# Local Development

Diese Repo ist so aufgebaut, dass du sie lokal auf diesem Mac weiterentwickeln und spaeter sauber nach GitHub spiegeln kannst.

## Ziel

Der lokale Ablauf soll drei Dinge gleichzeitig leisten:

1. die aktuelle Repo reproduzierbar starten
2. die GodMode-Struktur lokal weiterentwickeln
3. kleine, saubere GitHub-Iterationen ermoeglichen

## Voraussetzung

Vorhandene Toolchains auf diesem Mac sollten mindestens diese Klassen abdecken:

- `git`
- `node`, `npm`, `pnpm`
- `swift`, `xcodebuild`
- `flutter`, `dart`
- `codex`

## Erster Check

Im Repo-Root:

```bash
./scripts/check-local-env.sh
```

Wenn du diesen Mac auf den dokumentierten Global-Stand bringen willst:

```bash
./scripts/apply-global-codex-setup.sh
```

Optional ausfuehrlicher:

```bash
./scripts/check-local-env.sh --full
```

`--full` fuehrt zusaetzlich `flutter doctor -v` aus, was laenger dauern kann.

## Globale Profile fuer den Alltag

Die globale Beispielkonfiguration installiert vier Profile:

- `swiftui` fuer macOS- und iOS-Arbeit
- `web` fuer React, Next.js und Node.js
- `flutter` fuer Flutter und Dart
- `review` fuer Code- und Architektur-Reviews

CLI-Beispiele:

```bash
codex --profile swiftui
codex --profile web
codex --profile flutter
codex --profile review
```

Zum Pruefen des globalen Zustands:

```bash
./scripts/apply-global-codex-setup.sh --check
```

## Repo-Struktur fuer den Alltag

- `.codex/agents/` enthaelt die workflowbezogenen Agentenrollen
- `.agents/skills/` enthaelt wiederverwendbare Prozeduren und stack-spezifische Guidance
- `reports/generated/` ist fuer lokale, generierte Reports gedacht
- `state/` ist fuer lokalen Workflow-Zustand gedacht

## Empfohlener Arbeitsablauf

1. `git pull --ff-only`
2. neue Arbeitsbranch mit `codex/`-Prefix anlegen
3. `./scripts/check-local-env.sh`
4. optional `./scripts/apply-global-codex-setup.sh`
5. Codex aus dem Repo-Root starten
6. fuer groessere Aufgaben den GodMode-Workflow und passende Stack-Skills nutzen
7. nur die relevanten Validierungen laufen lassen
8. kleine Commits vorbereiten
9. erst nach expliziter Freigabe pushen

## Welche Skills hier zuerst sinnvoll sind

- `godmode-workflow` fuer groessere, mehrstufige Aufgaben
- `apple-platforms` fuer SwiftUI/macOS/iOS
- `web-platforms` fuer React, Next.js und Node.js
- `flutter-dart` fuer Flutter und Dart
- `release-manager` fuer Release-Impact und Changelog

## GitHub-Iteration

Fuer dieses Repo gilt bewusst ein einfacher, robuster Zyklus:

1. lokal reproduzieren
2. lokal fixen
3. lokal verifizieren
4. commit vorbereiten
5. push nur mit explizitem Go

## Noch nicht Teil dieses Schritts

- eine eigene GUI oder Web-App fuer das Agentensystem
- eine vollautomatische Runtime ausserhalb von Codex
- CI/CD oder Release-Automation

Diese Dinge koennen spaeter folgen, wenn die lokale Referenzstruktur stabil ist.
