# AGENTS.md

## Supply-chain checks for AUR updates

`electron45-bin` is an AUR fork (`upstream` is
`https://aur.archlinux.org/electron45-bin.git`). Before importing an upstream
update or pushing packaging changes:

- Review the AUR git history and diffs, not just the latest snapshot. After
  the initial import, only `_subver`, checksums and `.SRCINFO` should change;
  treat changes to source URLs, `prepare()` or `package()` as a red flag.
- Confirm source URLs point at the official
  `https://github.com/electron/electron/releases` assets.
- Download the archives independently and compare their SHA-256 sums with
  Electron's published `SHASUMS256.txt` and the GitHub release asset digests;
  do not trust the hashes in the AUR `PKGBUILD` alone.
- Inspect the archives for unexpected executables, scripts, symlinks or path
  traversal, and inspect launchers and `.install` files for hooks.
- Never accept new AUR checksums without repeating the upstream verification.
- Record what was verified in the commit message or `README.md`.
