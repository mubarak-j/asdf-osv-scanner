<div align="center">

# asdf-osv-scanner

[![Build](https://github.com/mubarak-j/asdf-osv-scanner/actions/workflows/build.yml/badge.svg)](https://github.com/mubarak-j/asdf-osv-scanner/actions/workflows/build.yml) [![Lint](https://github.com/mubarak-j/asdf-osv-scanner/actions/workflows/lint.yml/badge.svg)](https://github.com/mubarak-j/asdf-osv-scanner/actions/workflows/lint.yml) [![Release](https://img.shields.io/github/v/release/mubarak-j/asdf-osv-scanner)](https://github.com/mubarak-j/asdf-osv-scanner/releases) [![License](https://img.shields.io/github/license/mubarak-j/asdf-osv-scanner)](LICENSE)

[osv-scanner](https://google.github.io/osv-scanner/) plugin for the [asdf version manager](https://asdf-vm.com).

</div>

# Contents

- [About osv-scanner](#about-osv-scanner)
- [Dependencies](#dependencies)
- [Install](#install)
- [Usage](#usage)
- [Troubleshooting](#troubleshooting)
- [Contributing](#contributing)
- [License](#license)

# About osv-scanner

[osv-scanner](https://github.com/google/osv-scanner) is a vulnerability scanner from Google. It finds known vulnerabilities in your project dependencies, lockfiles, and container images. It reads its data from [OSV.dev](https://osv.dev), an open database of vulnerabilities across many ecosystems.

This plugin installs the prebuilt osv-scanner binaries from the [GitHub releases](https://github.com/google/osv-scanner/releases). It does not build osv-scanner from source.

# Dependencies

- `bash`, `curl`, and [POSIX utilities](https://pubs.opengroup.org/onlinepubs/9699919799/idx/utilities.html).
- [asdf](https://asdf-vm.com/guide/getting-started.html) 0.16 or later. Older asdf versions use different commands from the examples here.

The plugin supports these platforms:

| OS    | Architectures     |
| ----- | ----------------- |
| Linux | `amd64`, `arm64`  |
| macOS | `amd64`, `arm64`  |

The plugin supports osv-scanner 1.7.0 and later. Earlier releases use a different file name for the binary.

# Install

Add the plugin:

```shell
asdf plugin add osv-scanner https://github.com/mubarak-j/asdf-osv-scanner.git
```

If the plugin is in the [asdf-plugins](https://github.com/asdf-vm/asdf-plugins) registry, you can use the short form:

```shell
asdf plugin add osv-scanner
```

Install osv-scanner:

```shell
# Show all installable versions
asdf list all osv-scanner

# Install the latest version
asdf install osv-scanner latest

# Install a specific version
asdf install osv-scanner 2.7.1
```

Select a version:

```shell
# Use a version in the current project (writes ./.tool-versions)
asdf set osv-scanner 2.7.1

# Use a version everywhere (writes ~/.tool-versions)
asdf set -u osv-scanner latest

# Show the version in use
asdf current osv-scanner
```

Update the plugin:

```shell
asdf plugin update osv-scanner
```

Read the [asdf documentation](https://asdf-vm.com/manage/versions.html) for more ways to manage versions.

# Usage

Scan a project directory and all of its subdirectories:

```shell
osv-scanner scan source -r .
```

Scan one lockfile:

```shell
osv-scanner scan source -L package-lock.json
```

Scan a container image:

```shell
osv-scanner scan image alpine:3.20
```

Read the [osv-scanner usage guide](https://google.github.io/osv-scanner/usage/) for all commands and options.

The examples above use the osv-scanner 2.x commands. If you install a 1.x version, use the [1.x documentation](https://github.com/google/osv-scanner/tree/v1.9.2/docs) instead.

# Troubleshooting

If an install fails with `curl: (56) The requested URL returned error: 404`, that version has a git tag but no GitHub release. This applies to versions 1.7.1, 1.8.0, 2.3.4, and 2.3.7. Install a different version.

If you see `Unsupported OS` or `Unsupported architecture`, osv-scanner publishes no binary for your platform. Refer to the [Dependencies](#dependencies) section for the supported platforms.

# Contributing

Contributions of any kind are welcome. Read the [contributing guide](contributing.md).

[Thanks goes to these contributors](https://github.com/mubarak-j/asdf-osv-scanner/graphs/contributors)!

# License

See [LICENSE](LICENSE) © [Mubarak Jama](https://github.com/mubarak-j/)
