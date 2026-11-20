# AppleFetch 1.0.0 — Logo refinement

Mac-oriented terminal system information utility, built from the existing AppleFetch codebase. Not a complete Fastfetch fork.

## Changes
- Removed the Fastfetch-inspired / `original` theme from the settings selector. Previously saved `original` settings migrate to `modern`.
- Reworked the default Apple silhouette to include a separate leaf, an asymmetric body, a visible bite, and distinct bottom lobes.
- Reworked Classic to use a filled beige Macintosh body with a dark screen, disk slot and keyboard base.
- Uses solid dot-style Unicode artwork instead of dense block glyphs.
- Preserved six-stripe Retro coloring and the existing color customization options.
- Renamed CPU Details to CPU Configuration and GPU Details to Graphics Driver. CPU clock from Linux policy0 is labeled explicitly as the first cluster rather than an overall CPU clock.

## Build / install

```sh
make clean && make && make check
sudo make install
applefetch
applefetch --settings
```

Uninstall: `sudo make uninstall` or `sudo ./uninstall.sh`.


### Version 1.2.3

Both logos have been reduced approximately 20–25% in terminal width and height. The classic Macintosh keeps its screen, case, rainbow badge and keyboard details. The compact assets are shared by normal output and live preview.
