<div align="center">

# asdf-osv-scanner [![Build](https://github.com/mubarak-j/asdf-osv-scanner/actions/workflows/build.yml/badge.svg)](https://github.com/mubarak-j/asdf-osv-scanner/actions/workflows/build.yml) [![Lint](https://github.com/mubarak-j/asdf-osv-scanner/actions/workflows/lint.yml/badge.svg)](https://github.com/mubarak-j/asdf-osv-scanner/actions/workflows/lint.yml)

[osv-scanner](https://google.github.io/osv-scanner/) plugin for the [asdf version manager](https://asdf-vm.com).

</div>

# Contents

- [Dependencies](#dependencies)
- [Install](#install)
- [Contributing](#contributing)
- [License](#license)

# Dependencies

- `bash`, `curl`, and [POSIX utilities](https://pubs.opengroup.org/onlinepubs/9699919799/idx/utilities.html).
- The plugin supports osv-scanner 1.7.0 and later on Linux and macOS, for `amd64` and `arm64`.

# Install

Plugin:

```shell
asdf plugin add osv-scanner
# or
asdf plugin add osv-scanner https://github.com/mubarak-j/asdf-osv-scanner.git
```

osv-scanner:

```shell
# Show all installable versions
asdf list-all osv-scanner

# Install specific version
asdf install osv-scanner latest

# Set a version globally (on your ~/.tool-versions file)
asdf global osv-scanner latest

# Now osv-scanner commands are available
osv-scanner --version
```

Check [asdf](https://github.com/asdf-vm/asdf) readme for more instructions on how to
install & manage versions.

# Contributing

Contributions of any kind welcome! See the [contributing guide](contributing.md).

[Thanks goes to these contributors](https://github.com/mubarak-j/asdf-osv-scanner/graphs/contributors)!

# License

See [LICENSE](LICENSE) © [Mubarak Jama](https://github.com/mubarak-j/)
