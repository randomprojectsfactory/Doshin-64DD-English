# RC1 testing and known limits

## Evidence

| Check | Result and scope |
| --- | --- |
| EverDrive64 Pro / 64DD disk image | Project owner reports all 16 monument route unlocks and accepts Test10 for RC. Firmware [v26.1014](https://krikzz.com/pub/support/everdrive-64/pro-series/firmware/ed64-pro-fw-v26.1014.efu). |
| 19 regression groups | Passed. Selected native CPU paths run in an isolated harness; some audio/GPU dependencies are substituted. |
| 734 English script entries | No Japanese characters or TODO/TBD/FIXME markers in final English fields; installed text reconciled with the ledger. |
| IPL text scan | 90 candidate byte strings: 2 binary false positives, 76 old diary tails after replacement tokens, 12 superseded pool tails. Known references/replacements checked; these are not 90 visible untranslated strings. |
| Audio preservation | First three sections of all 335 banks identical to original. |
| Clean patch round trip | Expected RC1 output hash reproduced; original clean save partition retained. |
| Standalone emulators / cores | Full-game compatibility unverified; reports requested. |
| MiSTer FPGA / N64 core with 64DD support | Supported in initial hardware testing (17 November 2026): project owner reports RC1 boots and the UI, subtitles and text display without issues. Tested core: `N64_20260726.rbf` (latest official release at installation), NTSC PIF and Japanese retail IPL v1.2. Save/power-cycle/reload and full monument progression are not yet confirmed on MiSTer. |
| SummerCart64 | Unverified; reports requested. |
| Original 64DD drive | Untested. |

## Useful test cases

- Boot; start a new game; save; power-cycle; reload and verify progress.
- Watch the opening and both speakers’ captions, including overlapping male/female speech.
- Open Book of Giants immediately after boot, then close/reopen; compare letter spacing and clipping.
- Unlock a monument during gameplay; check its description and the logo as the background changes.
- Read long monument descriptions and multi-page dialogue through to the end.
- Check love/hate icons and counters, full statistics, day-end one-line comments and female commentary.
- Take/review photos that trigger female reactions.
- Continue over several in-game days and through monument progression.

Include image SHA-256 before play, patch version, device/core/emulator and version, firmware, BIOS/IPL, renderer and steps to reproduce. Screenshots or short recordings help. Never upload a ROM, disk image or personal save to an issue.

## Known limits

- Original Japanese voices and some original artwork/logo remain intentionally.
- The inventory is bounded: rare messages, alternate resources and debug screens are not exhaustively proven English.
- Some Japanese audio transcriptions and DD-specific cultural references remain open to contextual feedback; English copy review is not a Japanese-source certification.
- During a cold font load, a brief interval without text may occur; the previous full-width fallback is suppressed.
- Existing saved-progress images do not match the clean input hash. Save migration is not provided in this release.
- Do not enable TYCONF.SU DEBUG option 15. Read the warning in the README.
- NDD-to-Z64 conversion is deferred until after the RC.

See [the machine-readable audit summary](audit.json). RC1 is the accepted Test10 binary under its release name, with no new game-code changes.
