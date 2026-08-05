# sandi

**sandi** is a fast, interactive command-line package search and
installation utility for macOS and Linux.

It builds a local cache of available packages to provide quick searches,
then lets you install one or more matching packages from a simple
interactive menu.

## Features

-   Fast local package searching
-   Automatic package cache management
-   Supports:
    -   Homebrew Formulae
    -   Homebrew Casks
    -   DNF
    -   YUM
    -   APT
-   Interactive package selection
-   Install one, many, or all matching packages
-   Automatic cache refresh when needed
-   Safe, atomic cache updates
-   Works on both macOS and Linux

## Requirements

### macOS

-   Homebrew

### Linux

One of:

-   DNF
-   YUM
-   APT

Python 3.10 or newer is recommended.

## Installation

Clone the repository:

``` bash
git clone https://github.com/<your-user>/sandi.git
cd sandi
chmod +x sandi.py
```

Optionally place it somewhere in your PATH:

``` bash
sudo cp sandi.py /usr/local/bin/sandi
```

## Usage

Search for a package:

``` bash
sandi ripgrep
```

Search using multiple terms:

``` bash
sandi python dev
```

Force a cache refresh:

``` bash
sandi --refresh neovim
```

Install every matching package:

``` bash
sandi --all ffmpeg
```

Run interactively:

``` bash
sandi
```

## Cache

Package metadata is stored in:

    ~/.sandi/cache/package.list

The cache is automatically rebuilt if it is missing, appears invalid, or
is older than one day.

## How it Works

1.  Detects the host operating system.
2.  Locates the native package manager.
3.  Builds (or refreshes) a searchable local package index.
4.  Searches package names using one or more search terms.
5.  Presents an interactive list of matches.
6.  Installs the selected package(s).

## Design Goals

-   Extremely fast searches
-   Minimal dependencies
-   Native package manager integration
-   Cross-platform behavior
-   Safe cache handling
-   Clean, readable code

## License

This project is licensed under the GNU General Public License v3.0
(GPL-3.0).

See the `LICENSE` file for details.
