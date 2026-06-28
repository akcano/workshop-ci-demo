# workshop-ci-demo

A worked example for running [Workshop](https://github.com/canonical/workshop)
actions in GitHub Actions with the
[`canonical/launch-workshop`](https://github.com/canonical/launch-workshop)
action.

It shows two things that are awkward to get from a hand-built CI container:

- **A release matrix from one definition.** `.workshop/dev-jammy.yaml` and
  `.workshop/dev-noble.yaml` differ only by base image, so the same
  `unit-tests` action runs on both Ubuntu 22.04 and 24.04.

- **SDK cache persistence.** The action's `cache` input keeps the uv download
  cache between runs, so third-party wheels are fetched once and reused.

See the how-to *How to run workshops in GitHub Actions* in the Workshop
documentation.
