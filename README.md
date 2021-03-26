# pre-commit-hook

For running pre-commit hooks for kyverno.

## Hooks Available

There are two hooks available:

* `kyverno-validate`
* `kyverno-test`

## Pre-Requisites

Kyverno CLI must be installed

[Please use these instructions](https://kyverno.io/docs/kyverno-cli/)

## Example Usage

create .pre-commit-config.yaml at the root of repo

```yaml
repos:
  - repo: https://github.com/kyverno/pre-commit-hook
    rev: v1.0.0
    hooks:
      - id: kyverno-test
        args: ["kyverno-policies"]
      - id: kyverno-validate
        args: ["kyverno-policies"]
```

*Note: the args for each hook should be the directory where your kyverno policies are stored*

then run:

`pre-commit install`
`pre-commit run --all-files`

Further configuration of pre-commit (to only run on push, for example) see the [Pre-commit Documentation](https://pre-commit.com)
