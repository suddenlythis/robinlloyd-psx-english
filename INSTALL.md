# Installing the Robin Lloyd English translation (v1.0)

The download contains only the changes to the game's data track, not the game.
You need your own disc image of **Robin Lloyd no Bouken (Japan)**.

## What you need

- The Redump version of Robin Lloyd no Bouken (Japan) (product code SLPS-02501): one
  `.cue` and two track `.bin` files, as Redump catalogues it.
- The file that gets patched must be exactly:

  | File | Size | SHA-1 |
  |---|---|---|
  | `Robin Lloyd no Bouken (Japan) (Track 1).bin` | 206,710,224 bytes | `4c68776b4a98b9af4c62a691102009827207ce16` |

  With any other file the patch refuses to apply. Track 2 (the CD audio,
  36,705,312 bytes) is not changed.
- xdelta3, or a front end for it such as Delta Patcher or xdelta UI.
  Rom Patcher JS in a web browser also applies `.xdelta` files.
- A PlayStation emulator. Tested on DuckStation.

## What is in the zip

| File | What it is |
|---|---|
| `RobinLloyd-EN-v1.0-Track01.xdelta` | The patch for Track 1, the game data |
| `Robin Lloyd EN.cue` | Optional cue sheet, only for the side-by-side alternative below. Most people do not need it |
| `README.txt` | The release notes |

## How to apply

Patch Track 1 with the `.xdelta`. Keep the file name, and open your usual `.cue`.
That is all.

### With Delta Patcher

1. **Original file** = your `Robin Lloyd no Bouken (Japan) (Track 1).bin`
2. **XDelta patch** = `RobinLloyd-EN-v1.0-Track01.xdelta`
3. Tick **Backup original file** in the settings, then **Apply patch**.

### With the command line

xdelta3 writes a new file, so rename the original first:

```
ren "Robin Lloyd no Bouken (Japan) (Track 1).bin" "Track 1 original.bin"
xdelta3 -d -s "Track 1 original.bin" RobinLloyd-EN-v1.0-Track01.xdelta "Robin Lloyd no Bouken (Japan) (Track 1).bin"
```

### Check the result

The patched file has this SHA-1 checksum:

| File | SHA-1 after patching |
|---|---|
| Track 1 | `67da7f255b77549fccec95bcc6309f509bab2105` |

## Alternative: keep the Japanese and English discs side by side

Leave your files alone, save the patched Track 1 as `Robin Lloyd EN (Track 1).bin`
in the same folder, and open `Robin Lloyd EN.cue` from the zip. That cue lists the
patched Track 1 and your original Track 2. If your files are named differently, edit
the names in it.

## After patching

Start a new game or load an in-game save. A save state made on the Japanese game
keeps the old program and text in memory, so load the game normally instead.
In-game saves (memory card) work with both versions.

Controls, as the original manual gives them: Circle examines, talks and confirms,
Cross cancels (hold it to walk slowly), Triangle opens the item screen and Square
opens the config screen. When examining something up close, L1 / R1 / L2 / R2 turn
it. Select is not used, and analog mode is not used (vibration is supported).
If the game does not react to the pad, set the controller type to Digital Controller.

## Tested on

DuckStation. Not tested on other emulators or on real hardware.
