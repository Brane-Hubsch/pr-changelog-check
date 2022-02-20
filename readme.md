# PR Changelog Check | Github Action

This action will make sure that the changelog was edited for any created pull request into give branch. In the example below, the `development` branch.

```
name: Check Changelog

on:
  pull_request:
    branches: [development]
  workflow_dispatch:

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      # Checks-out your repository under $GITHUB_WORKSPACE, so your job can access it
      - uses: actions/checkout@v2
        with:
          fetch-depth: 0
      # Check that changelog.md has changes
      - name: Check Changelog
        run: |
          if [[ $(git diff --exit-code origin/develop..HEAD -- docs/changelog.md) ]]; then
            echo "Changelog changed - Good work!"
            exit 0
          else
            echo "Missing Changelog entry - Please add to the unreleased section in changelog"
            exit 1
          fi
```
