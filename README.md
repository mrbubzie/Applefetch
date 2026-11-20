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

## Limitations

Linux/Asahi build and smoke tests run successfully. Artwork has not been visually verified in Konsole. GPU core count and P/E core breakdown are not yet reliably detected across models. Classic Mac OS 68k/PPC and BSD support have not been validated.

## 1.0.1 terminal artwork revision

- Rebuilt the modern Apple silhouette and classic Macintosh as 31-column dot matrices.
- Classic Macintosh includes a CRT screen, disk slot, front panel, and separate keyboard.
- Hardware labels now reserve 19 columns to avoid collisions with values.
- Theme preview uses the same renderer as the regular command.
- Wider terminal threshold for side-by-side settings preview (175 columns).

Run `make && make check` before installing. For terminal comparison use
`./applefetch --theme modern` and `./applefetch --theme classic`.


## 1.2.0 system readout
The default display now follows a Fastfetch-like information hierarchy, including KDE, window manager, CPU topology, GPU, memory, swap, disk, battery, locale and Flatpak counts when available. Values are collected locally; unsupported fields show Unavailable.

## Native builds and installation

This release intentionally ships **source only**, not a precompiled `applefetch` executable.
Run `make clean && make && make check && sudo make install` on the target machine.
The Makefile rebuilds the executable on every invocation, so an old x86-64 binary
cannot be accidentally installed on an Apple Silicon ARM64 machine.
Verify with `file /usr/local/bin/applefetch` and `applefetch --version`.
The classic theme uses a filled 31-column Macintosh illustration with a recessed
screen, drive slot, rainbow badge and keyboard. The modern theme has a shaped
leaf, right-side bite and rounded base. `NO_COLOR=1` disables ANSI colors.

## 1.2.0 logo geometry refinement

The modern Apple and classic Macintosh logos now use independently authored 31 × 25 dot-cell masks rather than the older stretched outlines. The modern mark has a tilted detached leaf, wider shoulders, a right-side bite and separated bottom lobes. The classic Macintosh has a recessed CRT, distinct case and floppy slot, colored badge and separate keyboard with key detail. Both are rendered using the same Unicode dot-cell renderer as the other themes; classic uses beige, charcoal, and subdued accents by default. `--theme modern` and `--theme classic` are available for direct comparison. The terminal font and its glyph width can affect the visual proportions.


### 1.2.0 artwork update
The modern Apple and compact Macintosh logo masks have been rebuilt at 35 × 29 cells. Source releases contain no executable; `make install` compiles for the local architecture.

## 1.2.0 artwork and layout update

The modern and classic dot-matrix logos have been rebuilt. Settings preview
renders the logo above the system readout, rather than clipping readout values
to the right of the logo. The footer is positioned after the full preview.
On narrow terminals the normal display also switches to a stacked layout.
This is a source-only release: build natively with `make clean && make`.


### 1.2.0 logo refinement
- Classic Macintosh: plain dark screen without facial features; compact keyboard and case.
- Modern Apple: slimmer 35-cell dot-matrix silhouette with a defined bite and leaf.
- Both use the existing color system and shared normal/preview renderer.

### Version 1.2.0
Rebuilt fixed-width dot-matrix logos and added preview vertical scrolling ([ and ]). Narrow previews stack to prevent horizontal clipping.


## Logo geometry (1.2.0)
Both logos use fixed 35-column character-cell dot matrices. The modern Apple silhouette and classic Macintosh are shared by the normal display and live settings preview. The classic Macintosh screen contains no face. Build locally with `make clean && make` to avoid incompatible prebuilt binaries.

## 1.2.3 reference-driven artwork

Both default logos use dot positions and per-dot RGB colors sampled from the supplied reference artwork. Normal output and theme preview share the same renderer. This is an approximation constrained by terminal character-cell aspect ratio, not a pixel-identical reproduction of the raster image.

### Version 1.2.3

Both logos have been reduced approximately 20–25% in terminal width and height. The classic Macintosh keeps its screen, case, rainbow badge and keyboard details. The compact assets are shared by normal output and live preview.
