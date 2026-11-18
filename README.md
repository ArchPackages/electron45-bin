# electron45-bin — Arch Linux package

Prebuilt **Electron 45** runtime for Arch Linux, repackaged from the official
upstream Linux binaries. The package provides `electron45`, so applications can
depend on the standard Arch package name while using the prebuilt runtime.

Current version: **45.3.4**

## Provenance

Forked from the AUR package **electron45-bin**:

<https://aur.archlinux.org/packages/electron45-bin>

Originally packaged by **zxp19821005** and co-maintained by **Yurii Kolesnykov**,
based on Arch's `extra/electron*` packaging by **Bruno Pagani** and
**Caleb Maclennan**. Many thanks to them and to the Electron developers.

This fork is maintained by **Miroslav Pavleski** <miroslav@pavleski.net> and is
published through the [ArchPackages pacman repository](https://archpackages.github.io/archrepo/).

## Notes

- The package repackages the official `electron-v45.3.4-linux-x64.zip` and
  `chromedriver` release artifacts; it does not build Chromium from source.
- `chrome-sandbox` is installed setuid root as shipped by the AUR packaging.
- The launcher reads flags from `~/.config/electron45-flags.conf` (or
  `~/.config/electron-flags.conf`).

Build with `makepkg -f`; install with `pacman -U`.
