# Deplift Action

Automate dependency updates in my GitHub reops using [Deplift](https://github.com/szhsin/deplift), run tests and builds, and create a pull request—all with a single GitHub Action.

## Workflow Example

```yaml
name: Dependency update (deplift) # every Friday at 16:00 UTC

on:
  schedule:
    - cron: "0 16 * * 5"
  workflow_dispatch:

permissions:
  contents: write
  pull-requests: write

jobs:
  update-dependencies:
    runs-on: ubuntu-latest

    steps:
      - name: Update dependencies with Deplift
        uses: szhsin/deplift-action@v1
        with:
          node-version: 24
```
