# get-latest-python-version

This action helps get the most recent released Python versions.

## Basic usage

See the action.yaml for all inputs.
For now, they are quite restrictive:
the only option specifiable is ``last-n-minor-release``.

However, the associated Python script has much more flexibility.
We welcome contributions extending the flexibility to the action,
or updating the script itself!

Examples:

The below workflow sets up a Python environment
with the *previous* stable minor release.
e.g. Right now, 3.10 is the most recent stable minor release;
this will set up a Python 3.9 environment.
```yaml
steps:
- uses: actions/checkout@v3

- id: get-python-version
  uses: MDAnalysis/get-latest-python-version
  with:
    last-n-minor-release: 1

- uses: actions/setup-python@v4
  with:
    python-version: ${{ steps.get-python-version.outputs.python-version }}
```
