# PBCemu — Emulatoren für den PicoBoy Color Plus

Atari 2600, Commodore 64, NES, SG-1000, MSX, Master System, PC Engine,
Mega Drive, Game Gear und Game Boy (Color) in einer Firmware, mit Gerätewahl
und Spieleliste — oder die meisten Emulatoren als eigene Firmware. Zwei Geräte
am USB-C-Kabel spielen Atari 2600, C64, NES, SG-1000, MSX, Master System und
PC Engine zu zweit ([`docs/LINKSPIEL.md`](docs/LINKSPIEL.md)).

Fertige Firmware unter **Releases**: `pbcemu.uf2` (alles in einem) sowie
die Einzel-Firmwares. Bedienung, Aufbau und Flash-Aufteilung:
[`pbcemu/README.md`](pbcemu/README.md).

| Ordner | Inhalt | Lizenz |
|---|---|---|
| [`pbcemu`](pbcemu/) | Starter: Gerätewahl, Spieleliste, Optionen, USB-Laufwerk | GPL-3.0+ (Schrift Lato: OFL-1.1) |
| [`common`](common/) | Übergabe zwischen Starter und Emulatoren, Link-Spiel | GPL-3.0+ (`usblink.*`: GPLv2) |
| [`a2600`](a2600/) | Atari 2600 (eigener Kern), nur in PBCemu | GPL-3.0 |
| [`c64`](c64/) | Commodore 64 (Frodo4, MEGA65 OpenROMs) | GPL-2.0+ (OpenROMs: LGPL-3.0+) |
| [`nes`](nes/) | NES (QuickNES) | GPL-3.0 |
| [`sms`](sms/) | Master System, Game Gear und SG-1000 (SMS Plus, Z80 redcode, eigener PSG) | GPL-3.0 (Z80: LGPL-3.0+) |
| [`msx`](msx/) | MSX1 (eigener Kern, Z80 redcode, C-BIOS), nur in PBCemu | GPL-3.0 (Z80: LGPL-3.0+, C-BIOS: BSD-artig) |
| [`pce`](pce/) | PC Engine (pce-go) | GPL-3.0 |
| [`megadrive`](megadrive/) | Mega Drive (Gwenesis, 68000 Musashi 4.10, Z80 redcode, eigener YM2612/SN76489), mit Super Street Fighter II | AGPL-3.0 (68000: MIT, Z80: LGPL-3.0+) |
| [`gbc`](gbc/) | Game Boy Color und Game Boy (Peanut-GB) | GPL-3.0 |

Jeder Ordner hat seine eigene README und Lizenzdatei.

## Bauen

```bash
pbcemu/build.sh       # alle Emulatoren + Starter -> dist/pbcemu.uf2
nes/build.sh          # ein einzelner Emulator -> dist/nes.uf2
```

Werkzeuge und SDK: [`docs/BAUEN.md`](docs/BAUEN.md), Hardware:
[`docs/HARDWARE.md`](docs/HARDWARE.md). Spiele-ROMs liegen nicht bei.

Teil der Sammlung für den PicoBoy Color Plus, Übersicht: [pbc-plus](https://github.com/hcl1981/pbc-plus).
