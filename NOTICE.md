# NOTICE — third-party components and attributions

This repository's own RTL and tooling are **GPL-3.0** (see `LICENSE`). The
tree is not uniformly GPL-3.0; this file names every third-party component
compiled into the core, its authors, and its licence, with the paths as they
exist **in this repository**. File headers are preserved in place; where a
licence requires that its text accompany binary distributions, that text is
reproduced in full under *Licence texts for binary distribution* below.

## Compiled into the bitstream

| Component | Author(s) | Licence | Location |
|---|---|---|---|
| MiSTer framework | Till Harbaum, Alexey Melnikov (sorgelig), MiSTer-devel contributors | GPL-3.0-or-later | `sys/` |
| Machine RTL and MiSTer wrapper (this project) + TMS5220 speech model | spoonelli (machine RTL, `rtl/escape_mister.v`, `rtl/escape_hps_bridge.v`); TMS5220.vhd © 2020 d18c7db (Alex), based on MAME's `tms5220.cpp` | GPL-3.0 | `rtl/core/`, `rtl/escape_*.v` |
| TG68K.C 68000/68010 soft CPU (both 68ks) | Tobias Gubener (TobiFlex); patches by MikeJ, Till Harbaum, Rok Krajnc, others | LGPL-3.0-or-later (conveyed as part of the GPL-3.0 combined work: LGPL-3.0 is GPL-3.0 plus additional permissions) | `rtl/core/tg68kv/` (2 files with a documented LOCK-output change) + `rtl/TG68K/` (pristine support files) |
| T65 6502 soft CPU (JSA-I sound CPU) | Daniel Wallner, Mike Johnson, Wolfgang Scherr, Morten Leikvoll | BSD-style (OpenCores) | `rtl/T65/` — its "redistributions in synthesized form" clause is met by reproducing its notice, conditions and disclaimer under *Licence texts for binary distribution* below |
| jt51 YM2151 FM core | Jose Tejada (jotego) | GPL-3.0 | `rtl/jt51/` (pristine) + `rtl/core/jt51v/` (2 files with a documented per-channel gain change) |
| jt6295 OKI MSM6295 ADPCM core (JSA-II sound board: the Klax prototypes and Guts n' Glory; held in reset while Escape runs) | Jose Tejada (jotego) | GPL-3.0 | `rtl/jt6295/` (pristine, with its `LICENSE`) |

The RTL base lineage (Arcade-Atari-system1_MiSTer by d18c7db and
MiSTer-devel, GPL-3.0) is vendored through the files above rather than as a
submodule; provenance is recorded in each file's header.

## Corresponding source

This repository is the complete corresponding source of the core in
`releases/`: every file is vendored under `rtl/` and `sys/` (no submodules),
and its CI (`.github/workflows/build.yml`) rebuilds the release rbf from it.

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

## Licence texts for binary distribution

Reproduced verbatim from the file header, as this licence requires for
binary (synthesized) distributions. GPL-3.0 is `LICENSE`.

### T65 6502 core (`rtl/T65/`)

```
Copyright (c) 2002...2015
              Daniel Wallner (jesus <at> opencores <dot> org)
              Mike Johnson   (mikej <at> fpgaarcade <dot> com)
              Wolfgang Scherr (WoS <at> pin4 <dot> at>
              Morten Leikvoll ()

All rights reserved

Redistribution and use in source and synthezised forms, with or without
modification, are permitted provided that the following conditions are met:

Redistributions of source code must retain the above copyright notice,
this list of conditions and the following disclaimer.

Redistributions in synthesized form must reproduce the above copyright
notice, this list of conditions and the following disclaimer in the
documentation and/or other materials provided with the distribution.

Neither the name of the author nor the names of other contributors may
be used to endorse or promote products derived from this software without
specific prior written permission.

THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS"
AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO,
THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR
PURPOSE ARE DISCLAIMED. IN NO EVENT SHALL THE AUTHOR OR CONTRIBUTORS BE
LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR
CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF
SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS
INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN
CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE)
ARISING IN ANY WAY OUT OF THE USE OF THIS SOFTWARE, EVEN IF ADVISED OF THE
POSSIBILITY OF SUCH DAMAGE.
```
