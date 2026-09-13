# Homebrew Packages for Arch Linux Bootc

This repository contains [Homebrew](https://brew.sh) and [brew-proxy](https://codeberg.org/HastD/brew-proxy) meant to be used in [arch-bootc](https://github.com/bootcrew/mono) images.

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
pacman -S brew-proxy # optionally
```

## Projects using this repository

- [Apollo](https://getapollo.dev/)
- [Amethyris](https://github.com/Smujb/amethyris)

## Credits

Various files, including the systemd unit files and shell completion scripts, are taken from [Universal Blue's Homebrew packaging](https://github.com/ublue-os/brew) and are available under the terms of the Apache-2.0 license.

A patch used to modify Homebrew installer which then installs Homebrew to `src` directory, disables both cache and updating Homebrew during a build is based on a reference file from [secureblue's Homebrew RPM packaging](https://github.com/secureblue/homebrew) which does more modifying we don't need and is also available under the terms of the Apache-2.0 license.

Homebrew itself is available under the terms of the BSD-2-Clause license.

This repository is heavily based on [Hec's bootc repo](https://github.com/hecknt/arch-bootc-pkgs).
