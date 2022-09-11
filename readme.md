# Pull Request Changelog Check | Github Action

This action will make sure that the changelog was edited for any created pull request into given branch. In the example below, the `development` branch.

## Usage

```yaml
name: Check Changelog

on:
  pull_request:
    branches: [development] # <-- Change this to your branch that you want to watch

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      - uses: actions/checkout@v2
        with:
          fetch-depth: 0

      - uses: Brane-Hubsch/pr-changelog-check@v1
        with:
          changelog-path: "docs/changelog.md" # <-- Change this to your changelog path
```

---

[B&H](https://b-h.se)
