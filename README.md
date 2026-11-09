# PBCemu — Emulatoren für den PicoBoy Color Plus

Atari 2600, ZX Spectrum, ColecoVision, Commodore 64, Vectrex, NES, SG-1000,
MSX und MSX2, Amstrad CPC, Master System, Atari 7800, PC Engine, Mega Drive,
Game Gear, Game Boy (Color) und Arduboy in
einer Firmware, mit Gerätewahl und Spieleliste — oder die meisten Emulatoren
als eigene Firmware. Zwei Geräte am USB-C-Kabel spielen Atari 2600, Atari
7800, ColecoVision, C64, NES, SG-1000, MSX, ZX Spectrum, Amstrad CPC, Master
System, PC Engine und Mega Drive zu zweit, auch Sonic 2 im geteilten Bild
([`docs/LINKSPIEL.md`](docs/LINKSPIEL.md)); fehlt dem Partner das Spiel,
schickt man es übers Kabel mit. Game Boy (Color), NES, Master
System, Game Gear und Mega Drive speichern Spielstände als `.sav` neben dem
Spiel; Paddle-Spiele des Atari 2600 steuert man durch Drehen des Geräts,
für NES gibt es Game-Genie-Codes (`<Spiel>.cht`). Game Boys tauschen über
das Kabel Pokémon wie mit dem Linkkabel, Super-Game-Boy-Spiele erscheinen in
ihren Farben. Je Spiel einstellbar: Tastenbelegung, Farbpaletten, Scanlines,
Schwierigkeitsschalter; bei leeren Batterien blinkt im Spiel das
Batteriesymbol. Der Ton läuft mit 45 kHz (Mega Drive: 22 kHz); C64, CPC,
ZX Spectrum und MSX haben im Spiel ein Menü (Mitte + A) für Disketten- und
Bandwechsel, Einstellungen und einzelne Tasten. Der Arduboy übersetzt das
Spiel beim Laufen in ARM-Code und speichert sein EEPROM als `.sav`.

Fertige Firmware unter **Releases**: `pbcemu.uf2` (alles in einem) sowie
die Einzel-Firmwares. Bedienung, Aufbau und Flash-Aufteilung:
[`pbcemu/README.md`](pbcemu/README.md).

| Ordner | Inhalt | Lizenz |
|---|---|---|
| [`pbcemu`](pbcemu/) | Starter: Gerätewahl, Favoriten, Spieleliste, Optionen, Spiele löschen, Batterieanzeige, USB-Laufwerk | GPL-3.0+ (Schrift Lato: OFL-1.1) |
| [`common`](common/) | Übergabe zwischen Starter und Emulatoren, Link-Spiel | GPL-3.0+ (`usblink.*`: GPL-2.0+) |
| [`a2600`](a2600/) | Atari 2600 (eigener Kern, NTSC und PAL), Atari 7800 (eigener Kern mit MARIA und POKEY) und Vectrex (eigener Kern, 6809, VIA, Analogteil), nur in PBCemu | GPL-3.0 (Vectrex-ROM: siehe `a2600/LICENSE.vectrex`) |
| [`zx`](zx/) | ZX Spectrum 48K/128K (eigener Kern, Z80 redcode), Bänder und Snapshots, nur in PBCemu | GPL-3.0 (Z80: LGPL-3.0+; ROMs: Amstrad, siehe `zx/roms/LICENSE.roms`) |
| [`cpc`](cpc/) | Amstrad CPC 6128 (eigener Kern, Z80 redcode), Disketten, Kassetten, Snapshots, nur in PBCemu | GPL-3.0 (Z80: LGPL-3.0+; ROMs: Amstrad/Locomotive, siehe `cpc/roms/LICENSE.roms`) |
| [`c64`](c64/) | Commodore 64 (Frodo4, MEGA65 OpenROMs), D64, T64, PRG, CRT | GPL-2.0+ (OpenROMs: LGPL-3.0+) |
| [`nes`](nes/) | NES (QuickNES) | GPL-3.0 |
| [`sms`](sms/) | Master System, Game Gear und SG-1000 (SMS Plus, Z80 redcode, eigener PSG), in PBCemu auch ColecoVision mit Super Game Module | GPL-3.0 (Z80: LGPL-3.0+) |
| [`msx`](msx/) | MSX1 und MSX2 (eigener Kern mit V9938, Z80 redcode, C-BIOS; für BASIC/MSX-DOS die Original-ROMs vom Laufwerk), nur in PBCemu | GPL-3.0 (Z80: LGPL-3.0+, C-BIOS: BSD-artig) |
| [`pce`](pce/) | PC Engine (pce-go) | GPL-3.0 |
| [`megadrive`](megadrive/) | Mega Drive (Gwenesis, 68000 Musashi 4.10, Z80 redcode, eigener YM2612/SN76489), mit Super Street Fighter II und Link-Spiel | AGPL-3.0 (68000: MIT, Z80: LGPL-3.0+) |
| [`arduboy`](arduboy/) | Arduboy (eigener ATmega32U4-Kern, das Spiel beim Laufen taktgenau in ARM-Code übersetzt), Spiele als `.hex`, nur in PBCemu | GPL-3.0+ (Plattformteil: MIT, `arduboy/LICENSE.picoboygb`) |
| [`gbc`](gbc/) | Game Boy Color und Game Boy (Peanut-GB), Super-Game-Boy-Farben, Linkkabel | GPL-3.0 |

Jeder Ordner hat seine eigene README und Lizenzdatei.

## Bauen

```bash
pbcemu/build.sh       # alle Emulatoren + Starter -> dist/pbcemu.uf2
nes/build.sh          # ein einzelner Emulator -> dist/nes.uf2
```

Werkzeuge und SDK: [`docs/BAUEN.md`](docs/BAUEN.md), Hardware:
[`docs/HARDWARE.md`](docs/HARDWARE.md). Spiele liegen nicht bei. Die
eingebauten System-ROMs von ZX Spectrum und Amstrad CPC gehören Amstrad (beim
CPC auch Locomotive Software); Amstrad erlaubt ihre Weitergabe mit Emulatoren,
solange die Copyright-Meldungen bleiben und niemand Geld dafür nimmt. Sie
stehen nicht unter der Lizenz dieses Repositorys. Das BIOS der ColecoVision
liegt nicht bei: wer es hat, legt `coleco.rom` aufs Laufwerk, sonst startet
ein eigenes Mini-BIOS, das nur für wenige Spiele reicht. Das System-ROM des
Vectrex (mit Mine Storm) ist eingebaut wie beim Emulator vecx; Smith
Engineering hat 1992 erlaubt, die Vectrex-ROMs nicht kommerziell frei
weiterzugeben.

Teil der Sammlung für den PicoBoy Color Plus, Übersicht: [pbc-plus](https://github.com/hcl1981/pbc-plus).
