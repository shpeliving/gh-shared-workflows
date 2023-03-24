# json-syntax-validator

# Usage
## Input parameters
- `paths` - Required list of comma separated files to validate.

    ```
    # validate a list of JSON files
    with:
        paths: './schema/configuration.json,./app/definitions.json'

    # validate all JSON files in a folder
    with:
        paths: './configuration/*.json'
    ```

## Example

```
name: Validate JSON files
on:
  pull_request:
    branches:
      - main
  workflow_dispatch:

jobs:
  json_validator_job:
    runs-on: ubuntu-latest
    name: Validate JSON syntax
    steps:
      - uses: actions/checkout@v3
        with:
          token: ${{ secrets.ORGANIZATION_GITHUB_TOKEN }}
      - uses: shpeliving/gh-shared-workflows/.github/actions/json-syntax-validator@main
        with:
          paths: './configuration/*.json'
```