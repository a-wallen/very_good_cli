---
sidebar_position: 1
---

# Test 🧪

Run tests in a Dart or Flutter project with `very_good test`.

By default, this command will optimize your tests to run more efficiently by grouping them into a single entrypoint (see [this issue][cov_issue]).

## Usage

```sh
very_good test [arguments]
-h, --help                            Print this usage information.
    --coverage                        Whether to collect coverage information.
-r, --recursive                       Run tests recursively for all nested packages.
    --[no-]optimization               Whether to apply optimizations for test performance.
                                      (defaults to on)
    --exclude-coverage                A glob which will be used to exclude files that match from the coverage.
-x, --exclude-tags                    Run only tests that do not have the specified tags.
    --min-coverage                    Whether to enforce a minimum coverage percentage.
    --test-randomize-ordering-seed    The seed to randomize the execution order of test cases within test files.
    --update-goldens                  Whether "matchesGoldenFile()" calls within your test methods should update the golden files.

Run "very_good help" to see global options.
```

### Tests without pub install

Unlike `flutter test`, `very_good test` will always run your tests without installing the projects dependencies (i.e. `--no-pub` flag).

This is an optimization done by the cli because dependency installation is usually run once after cloning the repository. Conversely, running tests locally is usually done many times and it's often unnecessary to re-install dependencies prior to each test run.

If you need to install dependencies before running the tests with `very_good_cli`, be sure to run `very_good packages get` first.

[cov_issue]: https://github.com/flutter/flutter/issues/90225