# PR Changelog Check | Github Action

This action will make sure that the changelog was edited for any created pull request into given branch. In the example below, the `development` branch.

## Usage

```yaml
name: Check Changelog

on:
  pull_request:
    branches: [development]

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      - uses: actions/checkout@v2
        with:
          fetch-depth: 0

      - uses: Brane-Hubsch/pr-changelog-check@main
        with:
          changelog-path: "docs/changelog.md"
```
