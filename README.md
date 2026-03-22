# .github

Default workflows and community health files for all eriksjaastad repos.

## Reusable Workflows

### PR Label Check

Every PR must have a type label before merge: `feature`, `bug`, `chore`, `refactor`, `docs`, `test`, `hotfix`, `security`, or `perf`.

**To add to a repo**, create `.github/workflows/pr-label-check.yml`:

```yaml
name: "PR: Require Type Label"

on:
  pull_request:
    types: [opened, labeled, unlabeled, synchronize]

jobs:
  require-label:
    uses: eriksjaastad/.github/.github/workflows/require-pr-label.yml@main
```

Then enable branch protection on `main` with this as a required status check.
