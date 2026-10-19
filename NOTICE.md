# NOTICE — third-party components and attributions

This repository's own RTL and tooling are **GPL-3.0** (see `LICENSE`). The
tree is not uniformly GPL-3.0; this file names every third-party component
compiled into the core, its authors, and its licence, with the paths as they
exist **in this repository**. File headers are preserved in place; where a
licence requires that its text accompany binary distributions, that text is
in the named file's header and this NOTICE is the pointer to it.

## Compiled into the bitstream

| Component | Author(s) | Licence | Location |
|---|---|---|---|
| MiSTer framework | Till Harbaum, Alexey Melnikov (sorgelig), MiSTer-devel contributors | GPL-3.0-or-later | `sys/` |
| Machine RTL and MiSTer wrapper (this project) + TMS5220 speech model | spoonelli (machine RTL, `rtl/escape_mister.v`, `rtl/escape_hps_bridge.v`); TMS5220.vhd © 2020 d18c7db (Alex), based on MAME's `tms5220.cpp` | GPL-3.0 | `rtl/core/`, `rtl/escape_*.v` |
| TG68K.C 68000/68010 soft CPU (both 68ks) | Tobias Gubener (TobiFlex); patches by MikeJ, Till Harbaum, Rok Krajnc, others | LGPL-3.0-or-later | `rtl/core/tg68kv/` (2 files with a documented LOCK-output change) + `rtl/TG68K/` (pristine support files) |
| T65 6502 soft CPU (JSA-I sound CPU) | Daniel Wallner, Mike Johnson, Wolfgang Scherr, Morten Leikvoll | BSD-style (OpenCores) | `rtl/T65/` — its "redistributions in synthesized form" clause is satisfied by this documentation |
| jt51 YM2151 FM core | Jose Tejada (jotego) | GPL-3.0 | `rtl/jt51/` (pristine) + `rtl/core/jt51v/` (2 files with a documented per-channel gain change) |
| jt6295 OKI MSM6295 ADPCM core (JSA-II sound board: the Klax prototypes and Guts n' Glory; held in reset while Escape runs) | Jose Tejada (jotego) | GPL-3.0 | `rtl/jt6295/` (pristine, with its `LICENSE`) |

The RTL base lineage (Arcade-Atari-system1_MiSTer by d18c7db and
MiSTer-devel, GPL-3.0) is vendored through the files above rather than as a
submodule; provenance is recorded in each file's header.

## Known open item

`TMS5220.vhd` states it is based primarily on MAME's `tms5220.cpp`. If its
coefficient tables derive from that file, a BSD-3 notice for MAME's
speech-chip authors (Frank Palazzolo, Jarek Burczynski, Jonathan Gevaryahu,
Aaron Giles) is owed alongside it. Inherited from upstream, flagged rather
than silently shipped.

## Upstream

Development lives at
[spoonelli/Atari-Dual-68k](https://github.com/spoonelli/Atari-Dual-68k),
which also carries the **Analogue Pocket build's** additional components
(agg23's MIT `psram.sv`, the proprietary Analogue APF framework) and the
MAME reference material (`reference/`, read for behaviour, never compiled) —
none of which are present in this repository. See that repository's
`NOTICE.md` for their inventory.

## Trademarks and content

This project distributes no ROM data and no copyrighted artwork. *Escape
from the Planet of the Robot Monsters* is a trademark of its rights holders.
Use only with software you are legally entitled to.
