# Update Dependencies

A shared job to update all dependencies and make a pull request.

If you like this, we recommend making your own fork and customizing it to your needs.

# Usage

To use this action, add the following to your workflow file:

```yaml
name: Update Dependencies

on:
  schedule:
    - cron: '0 12 * * 6'  # Every Saturday at 12:00 PM UTC
  workflow_dispatch:

jobs:
  update-dependencies:
    runs-on: ubuntu-latest
    permissions:
      contents: write       # Push branches
      pull-requests: write  # Create PRs
    steps:
      - name: Run dependency update
        uses: cloud-copilot/update-dependencies@main
```