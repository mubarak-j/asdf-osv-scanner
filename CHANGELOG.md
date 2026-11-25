# Changelog

## 1.0.0 (2026-11-25)

This is the first release of the asdf plugin for [osv-scanner](https://github.com/google/osv-scanner). The plugin installs osv-scanner 1.7.0 and later from the prebuilt GitHub release binaries.

### Features

* Install osv-scanner from its GitHub release binaries on Linux and macOS, for `amd64` and `arm64` ([#4](https://github.com/mubarak-j/asdf-osv-scanner/pull/4))
* List only versions 1.7.0 and later, because earlier releases use a different binary file name ([#4](https://github.com/mubarak-j/asdf-osv-scanner/pull/4))
* Find the latest version from the latest GitHub release, so `asdf install osv-scanner latest` works ([#4](https://github.com/mubarak-j/asdf-osv-scanner/pull/4))

### Documentation

* Add an osv-scanner overview, usage examples, a platform table, and a troubleshooting section to the README ([#6](https://github.com/mubarak-j/asdf-osv-scanner/pull/6))
* Use asdf 0.16+ commands such as `asdf set` and `asdf list all` in the README ([#6](https://github.com/mubarak-j/asdf-osv-scanner/pull/6))
* Explain how to test the plugin locally and from a branch in the contributing guide ([#6](https://github.com/mubarak-j/asdf-osv-scanner/pull/6))
* Add Build, Lint, Release, and License badges, and fix GitHub detection of the Apache-2.0 license ([#6](https://github.com/mubarak-j/asdf-osv-scanner/pull/6))

### Continuous Integration

* Group Dependabot updates for GitHub Actions into one weekly PR ([#7](https://github.com/mubarak-j/asdf-osv-scanner/pull/7))
* Run actionlint with `raven-actions/actionlint`, so Dependabot keeps it up to date ([#7](https://github.com/mubarak-j/asdf-osv-scanner/pull/7))
* Pin all GitHub Actions to commit SHAs ([#8](https://github.com/mubarak-j/asdf-osv-scanner/pull/8))
* Update `actions/checkout`, `release-please-action`, and `action-semantic-pull-request` ([#1](https://github.com/mubarak-j/asdf-osv-scanner/pull/1), [#8](https://github.com/mubarak-j/asdf-osv-scanner/pull/8))

### Known Issues

* Versions 1.7.1, 1.8.0, 2.3.4, and 2.3.7 have a git tag but no GitHub release. If you install one of these versions, the download fails with a 404 error.
