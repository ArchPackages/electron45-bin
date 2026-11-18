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

## Supply-chain verification

The 45.3.4 archives were checked against Electron's official release data:

- The x86_64 `electron` and `chromedriver` zips were downloaded independently
  and their SHA-256 sums match both
  [SHASUMS256.txt](https://github.com/electron/electron/releases/download/v45.3.4/SHASUMS256.txt)
  and the GitHub release asset digests.
- The aarch64 checksums match the official `SHASUMS256.txt` entries.
- The archives contain only the expected Electron files: no symlinks, path
  traversal, dotfiles, scripts, or install hooks.
- The AUR packaging has no patches, `.install` file, or post-install code.
  After the initial import, only `_subver`, checksums and `.SRCINFO` changed.

Re-verify every version bump against `SHASUMS256.txt` before updating the
checksums; do not accept AUR checksum changes without that comparison.

## Notes

- The package repackages the official `electron-v45.3.4-linux-x64.zip` and
  `chromedriver` release artifacts; it does not build Chromium from source.
- `chrome-sandbox` is installed setuid root as shipped by the AUR packaging.
- The launcher reads flags from `~/.config/electron45-flags.conf` (or
  `~/.config/electron-flags.conf`).

Build with `makepkg -f`; install with `pacman -U`.
