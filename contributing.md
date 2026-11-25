# Contributing

## Plugin layout

```text
bin/
├── download        # downloads the release binary
├── install         # copies the binary into the asdf install path
├── latest-stable   # finds the latest GitHub release
└── list-all        # lists versions from git tags
lib/
└── utils.bash      # shared functions for the scripts in bin/
```

## Test locally

The `asdf plugin test` command installs the plugin in a temporary location. Then it installs osv-scanner and runs a test command.

```shell
asdf plugin test <plugin-name> <plugin-url> [--asdf-tool-version <version>] [--asdf-plugin-gitref <git-ref>] [test-command*]
```

Test your local copy of the plugin. Run this command from the repository root:

```shell
asdf plugin test osv-scanner "$PWD" "osv-scanner --version"
```

Test one osv-scanner version:

```shell
asdf plugin test osv-scanner "$PWD" --asdf-tool-version 2.7.1 "osv-scanner --version"
```

## Test a branch

To test a branch, pass its name to `--asdf-plugin-gitref`. The branch can be local or pushed to GitHub.

```shell
# A local branch
asdf plugin test osv-scanner "$PWD" --asdf-plugin-gitref my-branch "osv-scanner --version"

# A branch on GitHub
asdf plugin test osv-scanner https://github.com/mubarak-j/asdf-osv-scanner.git --asdf-plugin-gitref my-branch "osv-scanner --version"
```

To try a branch with your normal asdf setup, add the plugin and switch it to the branch:

```shell
asdf plugin add osv-scanner https://github.com/mubarak-j/asdf-osv-scanner.git
asdf plugin update osv-scanner my-branch
```

## Lint and format

The project pins `shellcheck` and `shfmt` in `.tool-versions`. Install them with asdf, then run the scripts:

```shell
asdf plugin add shellcheck
asdf plugin add shfmt
asdf install

scripts/lint.bash     # runs shellcheck and shfmt in diff mode
scripts/format.bash   # rewrites files with shfmt
```

## Continuous integration

GitHub Actions runs the tests and the linters on each push to `main` and on each pull request. The build tests run on Linux and macOS.

## Pull requests

The pull request title must follow [Conventional Commits](https://www.conventionalcommits.org), for example `feat: add checksum verification`. A workflow in `.github/workflows/semantic-pr.yml` enforces this format.
