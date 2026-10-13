# DWARF2026: A Modern restyled GUI for pk2cmd in Linux

## Screenshot

![DWARF main window](doc/screenshot.png)

Dwarf is a graphical interface for `pk2cmd`, designed to program Microchip PIC microcontrollers using the Microchip Pickit programmer.

Originally a simple Python script, Dwarf has been heavily modernized in **2026** to provide a robust, modern development experience on Linux while retaining its easy-to-use nature. It automates common tasks with the PICkit 2 and Pickit 3 , removing the need to memorize lengthy command-line arguments.

## 2026 Modernization Updates

The project has been completely overhauled to use modern technologies and provide an enhanced user experience:

### Technology Stack
*   **Python 3:** Fully migrated to modern Python.
*   **GTK 3 & PyGObject:** The UI has been rewritten using modern GTK 3 bindings, ensuring compatibility with current Linux desktop environments.
*   **pk2cmd Compatibility:** Updated to work seamlessly with the modern, community-maintained versions of `pk2cmd` available on GitHub.

### Visual & Functional Enhancements
*   **Interactive HEX Viewer:** A built-in, scrollable HEX file viewer. It features an intelligent parser that identifies memory regions (Reset Vector, Interrupt Vector, Config Words, EEPROM) and highlights them.
*   **Hover Tooltips:** Hovering over any byte in the HEX viewer reveals a floating tooltip with its physical address and memory region name.
*   **Theme Awareness:** The application dynamically adapts to your system's GTK theme (Light or Dark mode). The HEX viewer's syntax highlighting and the status bar automatically adjust to ensure perfect readability and contrast.
*   **Integrated Details Panel:** The status and operation details are now seamlessly integrated into the main window via a toggleable bottom panel, replacing the old, intrusive pop-up dialogs.
*   **Modern Iconography:** Buttons have been updated to use modern GTK symbolic icons combined with text labels, guaranteeing visibility across all system themes and ensuring actions are clear and intuitive.


## Requirements

*   Python 3.x
*   PyGObject (`python3-gi`)
*   GTK 3
*   `pk2cmd` (see below)

## Installing pk2cmd

Dwarf requires the `pk2cmd` command-line tool to communicate with PICkit hardware. Dwarf does **not** include or distribute pk2cmd — you must install it separately.

### Option 1: Community Builds (Recommended)
Several community-maintained forks provide pre-built binaries:
*   [jaka-fi/pk2cmd](https://github.com/jaka-fi/pk2cmd) — supports PICkit 2, PICkit 3, and PKOB
*   [boborjan2/pk2cmd](https://github.com/boborjan2/pk2cmd) — fork with libusb-1.0 support

### Option 2: Build from Source
Clone any pk2cmd repository and compile:
```bash
cd pk2cmd
make linux
sudo cp pk2cmd /usr/local/bin/
```

### Option 3: PICkitPlus (Commercial)
[PICkitPlus](https://www.pickitplus.co.uk/) offers a commercial, fully maintained alternative with the latest device support.

### Making pk2cmd available
Place the `pk2cmd` binary in any directory on your `PATH`, for example:
*   `~/.local/bin/` (user-local, no root needed)
*   `/usr/local/bin/` (system-wide)

## Usage

Simply run the script:
```bash
./dwarf
```

If `pk2cmd` is not found, Dwarf will show a dialog with installation instructions.

## License

Dwarf is free software released under the **GNU General Public License v3** (GPL-3.0). See [LICENSE.txt](doc/LICENSE.txt) for details.

## Third-Party Notice

`pk2cmd` is proprietary software owned by Microchip Technology Inc., distributed under its own license terms. Dwarf is an independent GUI wrapper and does not include, bundle, or redistribute pk2cmd or its device files. See [NOTICE](NOTICE) for details.

