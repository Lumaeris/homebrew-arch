# Homebrew Packages for Arch Linux Bootc

Originally created for [stargaze](https://github.com/Lumaeris/stargaze), this repository contains an Homebrew package meant to be used in [arch-bootc](https://github.com/bootcrew/mono) images and [brew-proxy](https://codeberg.org/HastD/brew-proxy) for a more secure Homebrew setup.

## Using the repository

In order to install packages from this repository via `pacman`, you need to import the signing key:

```bash
pacman-key --init
pacman-key --recv-key F88AD54AC93B084021C2BB69FC179FA0288C0734 --keyserver keyserver.ubuntu.com
pacman-key --lsign-key F88AD54AC93B084021C2BB69FC179FA0288C0734
```

And add the following to `/etc/pacman.conf`:
```ini
[homebrew]
SigLevel = Required
Server = https://github.com/Lumaeris/homebrew-arch/releases/download/$repo
```

Afterwards, sync your repositories with `pacman -Sy`, and then install a package like so:

```bash
pacman -S homebrew
```

## Credits

Various files, including the systemd unit files and shell completion scripts, are taken from [Universal Blue's Homebrew packaging](https://github.com/ublue-os/brew) and are available under the terms of the Apache-2.0 license.

A slightly older installer patch which installs Homebrew itself to the src directory and disables both updating and caching is taken from [secureblue's Homebrew RPM packaging](https://github.com/secureblue/homebrew) and is also available under the terms of the Apache-2.0 license.

Homebrew itself is available under the terms of the BSD-2-Clause license.

This repository is heavily based on [Hec's bootc repo](https://github.com/hecknt/arch-bootc-pkgs).
