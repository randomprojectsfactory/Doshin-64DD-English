# Doshin the Giant — 64DD English

**v1.0-RC1 · Release candidate Patch · Nintendo 64DD disk image (.ndd) not provided**

An English localisation of **Kyojin no Doshin** for Nintendo 64DD, using Nintendo’s official European GameCube wording wherever a suitable counterpart exists, with new English for the original game’s additional material.

♥️[Download RC1](https://github.com/randomprojectsfactory/Doshin-64DD-English/releases/tag/v1.0-RC1) · ⭐️[Instruction booklet (PDF)](https://github.com/randomprojectsfactory/Doshin-64DD-English/releases/download/v1.0-RC1/Doshin_64DD_English_Instruction_Booklet_v1.0.pdf) · ⭐️[Controls booklet (PDF)](https://github.com/randomprojectsfactory/Doshin-64DD-English/releases/download/v1.0-RC1/Doshin_64DD_English_Controls_Booklet_v1.0.pdf) · ⭐️[Strategy guide (PDF, 327 MB)](https://github.com/randomprojectsfactory/Doshin-64DD-English/releases/download/v1.0-RC1/Doshin_Guide_English_Reading_Edition_v1.0.pdf) (Thanks Iris, Tea and Coddie for the editing!) · [Translation notes](TRANSLATION_NOTES.md) · [Testing and known limits](docs/TESTING.md) · 🫠 [Report a problem](https://github.com/randomprojectsfactory/Doshin-64DD-English/issues/new/choose) 

## What it covers

- Main narration, opening subtitles, additional male speech and female commentary, including recap/photo contexts.
- All 16 monument descriptions and titles, end-of-day comments and the islanders’ diary.
- Inventoried menus, Book of Giants, statistics, notifications, photo controls, error messages and credits.
- Readable English layout, additional dialogue pages, centred female captions and preserved hearts, skulls, arrows and controller pictograms.
- Original Japanese audio. This is a subtitle/text patch, not an English dub.

The script ledger contains **734 entries**; UI and graphical text are additional. Some original Japanese artwork, including the title logo, remains. Rare states and debug-menu coverage are not exhaustively verified. This is an RC, not a guarantee that will work on every possible emulation core and flashcard.

## Tested hardware

**EverDrive64 Pro:** tested running the 64DD disk image. The tester reports completing the **16-monument route unlocks**, using [EverDrive64 Pro firmware v26.1014](https://krikzz.com/pub/support/everdrive-64/pro-series/firmware/ed64-pro-fw-v26.1014.efu) (tested 15 November 2026). The latest test build was accepted for RC.

RC1 is byte-identical to clean Test10; only the distribution name and documentation changed. Nineteen software regression groups passed. These exercise selected native CPU paths, text storage, layout and asset integration; they are not a full-game emulator playthrough. Original audio data across 335 banks was verified unchanged, and patch application reproduces the expected image exactly.

**MiSTer FPGA:** supported in initial hardware testing on 17 November 2026 with `N64_20260726.rbf` (the latest official N64/64DD core release at installation), NTSC PIF and Japanese retail 64DD IPL v1.2. The project owner reports that RC1 boots and the UI, subtitles and text display without issues. Save/power-cycle/reload and full monument progression remain to be confirmed on MiSTer.

**Testing requested:** standalone emulators and cores, **SummerCart64**, and further MiSTer coverage. Standalone emulators and SummerCart64 remain unverified. Please report the exact hardware/core/emulator version, firmware, BIOS/IPL setup, renderer, boot/save/reload results and any text or subtitle problems. See [the test checklist](docs/TESTING.md).

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
- Strategy guide: original Japanese guide scans by Ozidual; English translation prepared for this project.
- Community reference: **[64DD.org — Doshin tips](https://64dd.org/tips_doshin.html)**, including its debug-mode warning and linked original research.

This is an unofficial, non-commercial fan patch, not endorsed by Nintendo. No original game images, GameCube assets or personal saves are distributed here.

## Debug-menu warning

**Do not enable TYCONF.SU DEBUG, option 15.** [64DD.org warns](https://64dd.org/tips_doshin.html) that it may corrupt an SD card on a flashcart and cause glitches in emulation. The [original community report](https://krikzz.com/forum/index.php?topic=5882.0) specifically describes an ED64 v2.5 crash and SD corruption. This project has not tested that option or established its safety on EverDrive64 Pro, SummerCart64, MiSTer or emulators. Debug-menu localisation is outside the verified coverage.

## License and third-party rights

Original contributions are available under the [custom Attribution / Non-Commercial / Share-Alike / No AI Training License v1.1](LICENSE.MD). Free non-commercial use and sharing are permitted subject to its conditions. **No sale, resale, paid bundling or other commercial exploitation is permitted except for a verified underlying intellectual-property rightsholder under Section 3.1, after proof and written confirmation.** Owning a game or cartridge does not qualify.

**Attribution and share-alike are required:** retain credits, identify changes and license shared adaptations of the covered contributions under the same custom license. This does not relicense third-party game or translation material.

**AI/LLM training, fine-tuning, distillation and model evaluation or improvement require separate explicit written permission.** The commercial exception does not grant AI-training rights.

Third-party games, existing translations, artwork and firmware are excluded from this grant and retain their own rights and terms. See [Third-party notices](THIRD_PARTY_NOTICES.md) and the existing credits. This is a restrictive custom license, not an open-source license.
