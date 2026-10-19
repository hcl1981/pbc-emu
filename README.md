# PBCemu — Emulatoren für den PicoBoy Color Plus

Commodore 64, NES, Master System, PC Engine, Mega Drive, Game Gear und
Game Boy (Color) in einer Firmware, mit Gerätewahl und Spieleliste — oder
jeder Emulator als eigene Firmware.

Fertige Firmware unter **Releases**: `pbcemu.uf2` (alles in einem) sowie
die Einzel-Firmwares. Bedienung, Aufbau und Flash-Aufteilung:
[`pbcemu/README.md`](pbcemu/README.md).

| Ordner | Inhalt | Lizenz |
|---|---|---|
| [`pbcemu`](pbcemu/) | Starter: Gerätewahl, Spieleliste, Optionen, USB-Laufwerk | GPL-3.0+ (Schrift Lato: OFL-1.1) |
| [`common`](common/) | Übergabe zwischen Starter und Emulatoren | GPL-3.0+ |
| [`c64`](c64/) | Commodore 64 (Frodo4, MEGA65 OpenROMs) | GPL-2.0+ (OpenROMs: LGPL-3.0+) |
| [`nes`](nes/) | NES (QuickNES) | GPL-3.0 |
| [`sms`](sms/) | Master System und Game Gear (SMS Plus) | GPL-3.0 |
| [`pce`](pce/) | PC Engine (pce-go) | GPL-3.0 |
| [`megadrive`](megadrive/) | Mega Drive (Gwenesis), mit Super Street Fighter II | AGPL-3.0 |
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
