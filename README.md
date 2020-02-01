# sgrep-rules

[![CircleCI](https://circleci.com/gh/returntocorp/sgrep-rules.svg?style=svg)](https://circleci.com/gh/returntocorp/sgrep-rules)

This is an repository containing rules written for [sgrep](https://sgrep.dev), organized by language. Go to the main sgrep documentation for details on sgrep and the syntax for the yaml files in this repository.

## Running Rules in CI/Pre-Commit/Developer Workflow

If you want run these rules rather than write them, check out the easy-to-use [bento.dev](https://bento.dev)

## Contributing 

Please make a PR to submit your rules!

## Help

Contact the team at [sgrep@r2c.dev](mailto:sgrep@r2c.dev) for help.

## Testing Rules

A testing system is available which can be used to check the rules against example source code files.

If you wrote a rule in a yaml named `eqeq-bad.yaml` with a rule id named `my-eqeq-bad`, you could put a file in the same directory named eqeq-bad.py (it just needs to have the same name except for the extension as eqeq-bad.yaml). Then:

```python
# ruleid:my-eqeq-bad
x == x
```

Running `make test` will execute the test suite, and if `my-eqeq-bad` does not fire on the line below the comment, your rule will fail.

If you have a rule that is not working, but you want to commit it soo it's documented but not fail the tests, use `#todoruleid:...`:

```python
# todoruleid:my-eqeq-bad
x != x
```