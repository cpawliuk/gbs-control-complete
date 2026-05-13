# GBS-Control-Complete 1.4.0

GBS-Control-Complete is an enhanced fork of [`gbs-control`](https://github.com/ramapcsx2/gbs-control), an open-source custom firmware project for GBS-8200 / GBS-8220 video converter boards commonly used in the retro gaming community as a low-latency scaler known as the **GBS-C** **(GBS-Control)**.

This fork focuses on restoring missing upstream features, improving usability, and expanding OSD/Web UI functionality for ESP8266-based GBS-C builds.

## Project Status

This fork is currently in maintenance mode.

No major planned feature development is expected, however upstream fixes, useful pull requests, and community-requested improvements may still be merged over time.

If there are features from the main `gbs-control` repository or open pull requests that should be integrated into this fork, feel free to open an issue or submit a pull request.

## Building and Flashing

This repository includes all required dependencies for building GBS-C firmware using the Arduino IDE and ESP8266 boards package.

Precompiled firmware builds are also available in the `build` directory for easier flashing.

## Features

- Low-latency upscaling for retro gaming
- Support for GBS-8200 and GBS-8220 boards
- Compatible with RGBS, RGBHV, VGA, SCART, and Component video
- Automatic handling of 240p / 480i mode switching
- Motion adaptive deinterlacing
- Web browser control interface using ESP8266 WiFi
- OLED and OSD menu support
- Enhanced FrameTime Lock controls
- Restored color correction controls
- Restored preset management functionality
- Improved Web GUI usability
- Precompiled firmware builds included

## What is GBS-C?

GBS-C (GBS-Control) is a custom firmware modification for inexpensive GBS-8200 / GBS-8220 scaler boards that transforms them into high-quality retro gaming scalers with features comparable to significantly more expensive hardware solutions.

It is commonly used with:

- Retro consoles
- PlayStation 2
- Sega Dreamcast VGA
- MiSTer FPGA
- Arcade hardware
- Home computers
- DOS PCs

## Included Components

- [`gbs-control`](https://github.com/ramapcsx2/gbs-control) — Original video processor firmware, modified for ESP8266.
- [`ESPAsyncWebServer`](https://github.com/me-no-dev/ESPAsyncWebServer) — Asynchronous web server library.
- [`ESPAsyncTCP`](https://github.com/me-no-dev/ESPAsyncTCP) — Async TCP library required by the web server.
- [`esp8266-oled-ssd1306`](https://github.com/ThingPulse/esp8266-oled-ssd1306) — OLED display library for ESP8266.
- [`package_esp8266com_index.json`](http://arduino.esp8266.com/stable/package_esp8266com_index.json) — Additional Boards Manager URL for ESP8266.

## Modifications and Features Added

- [`1.4.0`] Restored [Added remove presets feature - PR #496](https://github.com/ramapcsx2/gbs-control/pull/496) which was missing because the contributor edited the generated webui.html directly instead of index.html.tpl. Changes were lost on build. Initial implementation by [AlivE-git](https://github.com/AlivE-git).
- [`1.3.0`] Restored [Added color correction settings - PR #490](https://github.com/ramapcsx2/gbs-control/pull/490) which were missing because the contributor edited the generated webui.html directly instead of index.html.tpl. Changes were lost on build. Initial implementation by [AlivE-git](https://github.com/AlivE-git).
- [`1.2.0`] Improved the Web GUI in the FrameTime Lock section by replacing the single "Switch Lock Method" cycling button with explicit toggles for each method. This change makes it immediately clear which FrameTime Lock method is active, improving usability and removing the need to consult logs.

**Before:**

The active method was hidden; switching required pressing the arrow button and observing the effect.

![FrameTime Lock Method Screenshot 1](images/FrameTime-Lock-Method-README-IMG-1.png)

**After:**

Each method now has its own toggle button. The currently selected method is highlighted, allowing faster and more intuitive control.

![FrameTime Lock Method Screenshot 2](images/FrameTime-Lock-Method-README-IMG-2.png)
![FrameTime Lock Method Screenshot 3](images/FrameTime-Lock-Method-README-IMG-3.png)

- [`1.1.0`] Added an OSD menu option to enable scanlines and adjust strength using the same intensity levels as the Web GUI.

![Scanlines OSD Screenshot](images/Scanlines-README-IMG.png)

- [`1.0.0`] Updated include paths and `#include` directives to match current IDE/library expectations.
- [`1.0.0`] Adjusted build flags and settings for ESP8266 compatibility.
- [`1.0.0`] Patched code inconsistencies in `gbs-control` that caused compiler errors.
- [`1.0.0`] Ensured all dependencies are self-contained in this repository for reproducible builds.

You can compare these changes from the original sources by checking the [commit history](https://github.com/cpawliuk/gbs-control-complete/commits/main/).

## Credits

- [rama](https://github.com/ramapcsx2) — `gbs-control`
- [me-no-dev](https://github.com/me-no-dev) — `ESPAsyncTCP` and `ESPAsyncWebServer`
- [Daniel Eichhorn](https://github.com/squix78) & [Fabrice Weinberg](https://github.com/FWeinb) — `esp8266-oled-ssd1306`
- [Christopher Pawliuk](https://github.com/cpawliuk) — Modifications and Features Added in this package

## Versions

- [`gbs-control`] — based on commit e4e317a.
- [`ESPAsyncWebServer`] — based on commit ad3741d.
- [`ESPAsyncTCP`] — as of commit 191bdeb.
- [`esp8266-oled-ssd1306`] — as of commit f90368e.
