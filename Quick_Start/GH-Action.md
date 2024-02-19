# Quick Start
## GitHub actions
Manual start with GitHub Pages.

Create following action at `.github/workflows/docs.yaml`
```yaml
name: docs-actions
run-name: UpdateDocs
on:
  workflow_dispatch:
    inputs:
      base:
        description: "Base of docs"
        default: ""
      redocs_config:
        description: "URL to redocs config"
        default: ""
jobs:
  ReDocs-launch:
    runs-on: ubuntu-latest
    steps:
      - uses: RedSockActions/redocs@v0.0.14
        with:
          token: ${{ github.token }}
```

### "base" input
Defines what base url ReDocs will be based on

e.g. For repository "my-cool-company/my-cool-project"
base url by default will be "my-cool-project"

In case:
1. You want to change your default GitHub's domain
2. You ran organization level github-pages 

You might consider to change base url via "base" input

### "redocs_config" input
Defines url path to redocs config which contains 
a basic configuration for redocs to run

By default, action will try to get config from the root of the
branch it was launched from

e.g. If you've triggered this action from master branch - action
will try  to search for redocs.json at https://raw.githubusercontent.com/RedSockActions/redocs/master/redocs.json