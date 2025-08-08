
# Shopify Git Workflow

## Sample ci.yml
```bash
name: CI
on: [push, pull_request]

permissions:
  contents: read
  checks: write
  pull-requests: write
jobs:
  theme-check:
    name: Theme Check
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - name: Theme Check
        uses: shopify/theme-check-action@v2
        with:
          token: ${{ github.token }}
```