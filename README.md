# ABZG CAD Data Extractor

Extract **layers, geometry, text, blocks and dimensions** from a drawing and export
them to **CSV, Excel (.xlsx) or JSON** — from inside AutoCAD, BricsCAD or ZWCAD.

All three formats write the same rows and the same columns; pick according to what
you will do with the file next.

This repository hosts the released build and the user guide. It contains
**no source code**.

## Download

| Item | File |
|---|---|
| **Installer** (single file, ~1.4 MB) | [`ABZG-CadExtractor-Setup-1.0.0.exe`](ABZG-CadExtractor-Setup-1.0.0.exe) |
| **User guide** (English) | [`docs/USER-GUIDE.en.md`](docs/USER-GUIDE.en.md) |

## Supported CAD versions

| CAD | Supported versions |
|---|---|
| **AutoCAD** | **2025 / 2026 / 2027** |
| **ZWCAD** | **2025 / 2026** |
| **BricsCAD** | **V26** (BricsCAD 2026) |

These are **verified on real machines**: the payload installs, the command is
recognised, the window opens and data reads out. **Any other version has not been
tested** — that does not mean it cannot work, only that it has not been verified.

> ⚠️ **ZWCAD 2024 and earlier is not part of this package** — building that payload
> needs the assemblies from a ZWCAD 2024 installation. On those releases the plugin
> simply does not load: no effect, no error, and ZWCAD itself is unaffected.

One installer covers all of the above and installs per-user by default — **no
administrator rights needed**. See [§2 of the user guide](docs/USER-GUIDE.en.md)
for the details.

## Requirements

64-bit Windows. **`.NET Desktop Runtime 8.0 (x64)`** is needed only by the releases
that run on the modern managed runtime:

| Your release | Extra install needed? |
|---|---|
| AutoCAD 2025 / 2026 | .NET 8 |
| AutoCAD 2027 | .NET 10 |
| BricsCAD V26 | .NET 8 |
| ZWCAD 2025 / 2026 | No |

> It must be the **Desktop** Runtime, not the plain .NET Runtime. The UI is WPF, and
> without `Microsoft.WindowsDesktop.App` the plugin **fails to load and reports
> nothing at all**, which looks exactly like "the command does nothing".

The installer detects this for you and reports it before installing anything.

## Install

Run `ABZG-CadExtractor-Setup-1.0.0.exe` and double-click it. To preview what it would
do without changing anything:

```
ABZG-CadExtractor-Setup-1.0.0.exe --list
```

To uninstall: `ABZG-CadExtractor-Setup-1.0.0.exe --uninstall`, or remove
**ABZG CAD Data Extractor** from "Settings → Apps".

## Use

In the CAD command line:

```
ABZGEXTRACT
```

That opens the extraction window. Right-click, `Re-extract`, `Pick Objects` and
`Export` are covered in the [user guide](docs/USER-GUIDE.en.md).

![Main window](docs/images/preview-window.png)

## Documentation

- **[User Guide (English)](docs/USER-GUIDE.en.md)** — supported versions, requirements,
  installing, every command-line option, the interface, export formats, troubleshooting.

## License

Proprietary. The installer and this documentation are provided as-is for evaluation
and use by their intended recipients; no source code is distributed.
