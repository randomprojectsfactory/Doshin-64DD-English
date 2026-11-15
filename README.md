# Doshin the Giant — 64DD English

**v1.0-RC1 · Release candidate · Nintendo 64DD disk image (.ndd)**

An English localisation of **Kyojin no Doshin (Japan)** for Nintendo 64DD, using Nintendo’s official European GameCube wording wherever a suitable counterpart exists, with new English for the original game’s additional material.

[Download RC1](https://github.com/randomprojectsfactory/Doshin-64DD-English/releases/tag/v1.0-RC1) · [Translation notes](TRANSLATION_NOTES.md) · [Testing and known limits](docs/TESTING.md) · [Report a problem](https://github.com/randomprojectsfactory/Doshin-64DD-English/issues/new/choose)

## What it covers

- Main narration, opening subtitles, additional male speech and female commentary, including recap/photo contexts.
- All 16 monument descriptions and titles, end-of-day comments and the islanders’ diary.
- Inventoried menus, Book of Giants, statistics, notifications, photo controls, error messages and credits.
- Readable English layout, additional dialogue pages, centred female captions and preserved hearts, skulls, arrows and controller pictograms.
- Original Japanese audio. This is a subtitle/text patch, not an English dub.

The script ledger contains **734 entries**; UI and graphical text are additional. Some original Japanese artwork, including the title logo, remains. Rare states and debug-menu coverage are not exhaustively verified. This is an RC, not a guarantee that every possible screen has been checked.

## Tested hardware

**Hardware testing is currently limited to EverDrive64 Pro running the 64DD disk image.** The tester reports completing the **16-monument route unlocks**, using [EverDrive64 Pro firmware v26.1014](https://krikzz.com/pub/support/everdrive-64/pro-series/firmware/ed64-pro-fw-v26.1014.efu) (tested 15 November 2026). The latest test build was accepted for RC.

RC1 is byte-identical to clean Test10; only the distribution name and documentation changed. Nineteen software regression groups passed. These exercise selected native CPU paths, text storage, layout and asset integration; they are not a full-game emulator playthrough. Original audio data across 335 banks was verified unchanged, and patch application reproduces the expected image exactly.

**Testing requested:** standalone emulators and cores, **MiSTer**, and **SummerCart64**. These targets are currently unverified; this is a request for compatibility reports, not a claim that each supports this image. Please report the exact hardware/core/emulator version, firmware, BIOS/IPL setup, renderer, boot/save/reload results and any text or subtitle problems. See [the test checklist](docs/TESTING.md).

## How to patch

The release contains a patch, not a game image. Supply your own original Japanese dump. The GameCube disc is not needed to apply the patch.

1. Back up your original disk image and any existing progress.
2. Confirm the input is **64,931,840 bytes** and matches the SHA-256 below. A matching filename is not sufficient. Do not use an existing translation, a cartridge-converted `.z64`, a `.d64`, or an image modified by saved progress.
3. Extract `Doshin_64DD_English_v1.0-RC1_Patch.zip` from the release.
4. Apply `Doshin_64DD_English_v1.0-RC1.xdelta` with **xdelta3**. With [xdelta3](https://github.com/jmacd/xdelta/releases) installed, run:

```sh
xdelta3 -d -s "Kyojin no Doshin (Japan).ndd" "Doshin_64DD_English_v1.0-RC1.xdelta" "Doshin_64DD_English_v1.0-RC1.ndd"
```

5. Verify the output hash below **before playing**, then copy the `.ndd` to your supported device’s game directory. Keep the `.ndd` extension. This release does not provide a `.z64` cartridge conversion.

### SHA-256

| File | SHA-256 |
| --- | --- |
| Original Japanese input `.ndd` | `d9044b187c5545f8f791bafb8821c3dd365fb822cc6dc893b8792e8ecce56450` |
| Clean RC1 output `.ndd` | `155434901e77ccfed2ad024ec9712f204efaba7a6246d824f5de1a29a55f5eac` |
| RC1 `.xdelta` patch | `8da474168d940f4605ff8d70fbc7768b65cb45bb40a891745547123d402c7f45` |

Input and output size: **64,931,840 bytes**. Release download checksums are also provided in `SHA256SUMS.txt`.

On macOS/Linux, use `shasum -a 256 "filename"` (or `sha256sum`). In Windows PowerShell, use `Get-FileHash "filename" -Algorithm SHA256`.

### Saves

The tested EverDrive disk image stores progress in its writable disk area. Playing and saving can therefore change the `.ndd` hash. The hash above describes a freshly patched image only. **Back up the whole played image before replacing it.** The release patch expects the exact clean input and does not migrate personal progress. Do not overwrite your played image with a clean RC1. Cartridge-conversion save compatibility is not established.

## Translation and credits

See [Translation notes](TRANSLATION_NOTES.md) for per-category Nintendo reuse percentages, wording adaptations and Japanese/English tables. The project owner reports that a native English-speaking copywriter reviewed the English and returned no notes. Feedback remains welcome.

This project is **not based on Ozidual’s translation, patch or code**, and is not intended to replace or supersede that earlier project. Ozidual described it as [mothballed in May 2026](https://krikzz.com/forum/index.php?topic=5882.60).

- Original game, artwork, voices and official GameCube English: their respective rights holders, including Nintendo and the original development/localisation teams.
- Localisation project and hardware review: randomprojectsfactory.
- Community reference: **[64DD.org — Doshin tips](https://64dd.org/tips_doshin.html)**, including its debug-mode warning and linked original research.

This is an unofficial, non-commercial fan patch, not endorsed by Nintendo. No original game images, GameCube assets, manual scans or personal saves are distributed here.

## Debug-menu warning

**Do not enable TYCONF.SU DEBUG, option 15.** [64DD.org warns](https://64dd.org/tips_doshin.html) that it may corrupt an SD card on a flashcart and cause glitches in emulation. The [original community report](https://krikzz.com/forum/index.php?topic=5882.0) specifically describes an ED64 v2.5 crash and SD corruption. This project has not tested that option or established its safety on EverDrive64 Pro, SummerCart64, MiSTer or emulators. Debug-menu localisation is outside the verified coverage.
