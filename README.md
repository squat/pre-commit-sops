[![pre-commit.ci status](https://results.pre-commit.ci/badge/github/squat/pre-commit-sops/main.svg)](https://results.pre-commit.ci/latest/github/squat/pre-commit-sops/main)
# pre-commit-sops
`pre-commit-sops` is a [pre-commit](https://pre-commit.com) hook that detects [SOPS](https://getsops.io) secrets that are unencrypted or encrypted with the wrong key(s). `pre-commit-sops` uses your `.sops.yaml` file to match files to the correct keys.

`pre-commit-sops` is conservative by default and checks all files with `secret` anywhere in the path; that means all files with `secret` in their name or under a directory with `secret` in the name must be encrypted. This rule can be adjusted by modifying the values of the `files` or `exclude` keys in the hook's configuration.

## Installation

Add this to your `.pre-commit-config.yaml`

```yaml
-   repo: https://github.com/squat/pre-commit-sops
    rev: 0.1.0
    hooks:
    -   id: sops
```
