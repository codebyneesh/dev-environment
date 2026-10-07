# Homebrew Command Cheatsheet

## Basic Information

Check Homebrew version:

    brew --version

Display Homebrew configuration and environment information:

    brew config

Check the Homebrew installation for potential problems:

    brew doctor


## Searching & Installing

Search for a package:

    brew search <package>

View information about a package:

    brew info <package>

Install a package:

    brew install <package>

Uninstall a package:

    brew uninstall <package>

Reinstall a package:

    brew reinstall <package>


## Viewing Installed Packages

List installed packages:

    brew list

List installed packages with versions:

    brew list --versions

Check whether a specific package is installed:

    brew list <package>

Show only packages I explicitly installed:

    brew leaves


## Updating Packages

Update Homebrew's package definitions:

    brew update

See which installed packages are outdated:

    brew outdated

Upgrade all outdated packages:

    brew upgrade

Upgrade one package:

    brew upgrade <package>


## Cleanup

See what Homebrew would remove without actually removing it:

    brew cleanup --dry-run

Remove old package versions and cached files:

    brew cleanup


## Services

List services managed by Homebrew:

    brew services list

Start a service:

    brew services start <service>

Stop a service:

    brew services stop <service>

Restart a service:

    brew services restart <service>


## Taps

List configured taps:

    brew tap

Add a tap:

    brew tap <repository>

Remove a tap:

    brew untap <repository>

Example:

    brew tap hashicorp/tap


## Brewfile / Homebrew Bundle

Install everything declared in the Brewfile:

    brew bundle --file=Brewfile

Check whether the current machine satisfies the Brewfile:

    brew bundle check --file=Brewfile

List what `brew bundle` would install without installing it:

    brew bundle list --file=Brewfile

Create a Brewfile from the current machine:

    brew bundle dump

Overwrite an existing Brewfile with the current machine's packages:

    brew bundle dump --force

Remove packages that are installed but are not declared in the Brewfile:

    brew bundle cleanup --file=Brewfile

Preview what Brewfile cleanup would remove:

    brew bundle cleanup --file=Brewfile --dry-run


## Dependencies

Show a package's dependencies:

    brew deps <package>

Show installed packages that depend on a package:

    brew uses --installed <package>


## Troubleshooting

Show where a package is installed:

    brew --prefix <package>

Show detailed package information:

    brew info <package>

Check Homebrew for configuration problems:

    brew doctor
