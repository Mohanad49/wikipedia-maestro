# Mobile Automation Portfolio — Wikipedia Android

Maestro-based mobile automation suite targeting the 
[Wikipedia Android open-source app](https://github.com/wikimedia/apps-android-wikipedia).

![CI](https://github.com/Mohanad49/wikipedia-maestro/actions/workflows/maestro.yml/badge.svg)

## Stack
- **Maestro** — YAML-driven mobile test automation
- **Android Emulator** — Pixel 6, API 33
- **GitHub Actions** — CI execution on every push

## Test Coverage

| Flow | Description |
|------|-------------|
| `search_article` | Search for an article and verify content loads |
| `reading_list` | Save an article to reading list and verify |
| `language_switch` | Add Arabic language and verify UI updates |

## Project Structure

.maestro/
├── subflows/
│   ├── launch_and_onboard.yaml   # Reusable app launch + onboarding dismissal
│   └── navigate_to_search.yaml   # Reusable search navigation
├── tests/
│   ├── search_article.yaml
│   ├── reading_list.yaml
│   └── language_switch.yaml
└── run_all.yaml

## Run Locally

**Prerequisites:** Maestro installed, Android emulator running with Wikipedia installed.

```bash
# Run a single flow
maestro test .maestro/tests/search_article.yaml

# Run all flows
maestro test .maestro/run_all.yaml
```

## CI

Tests run automatically on every push via GitHub Actions 
using the `reactivecircus/android-emulator-runner` action on a macOS runner.