# Pull Request Changelog Checking | Github Action

Running this action will check and make sure that a specified changelog file was edited for any created pull request into given branch. In the example below, the `development` branch.

## Usage

```yaml
name: Check Changelog

on:
  pull_request:
    # Change this to your branch that you want to watch
    branches: [development]

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      - uses: actions/checkout@v3
        with:
          fetch-depth: 1

      - uses: Brane-Hubsch/pr-changelog-check@v2
        with:
          # Change this to your changelog path, defaults to docs/changelog.md
          changelog-path: "docs/changelog.md"
```

---

Created by [B&H](https://bh.studio)
