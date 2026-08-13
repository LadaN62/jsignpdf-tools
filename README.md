# JSignPdf Tools

**JSignPdf Tools** is an enhanced version of [JSignPdf](https://github.com/intoolswetrust/jsignpdf), focused on improving the desktop workflow for visible PDF signatures and technical document approval.

The project keeps the original JSignPdf signing capabilities while adding workflow and user-interface improvements developed on top of the upstream project.

> **Note:** JSignPdf Tools is an independent derivative project and is not the official JSignPdf distribution.

## Current enhancements

Compared with the upstream JSignPdf application, this project currently includes:

* **Improved visible-signature preview**

  * More accurate preview of the final signature appearance.
  * Improved correspondence between the preview and the signed PDF.
  * Better handling of display DPI and preview scaling.

* **Interactive signature placement**

  * Move the visible signature directly on the PDF preview.
  * Resize it interactively using the mouse.
  * Cursor feedback for moving and resizing the signature rectangle.

* **Improved signature rendering**

  * Adjustments to OpenPDF visible-signature rendering.
  * Improved text positioning and layout.
  * Improved timestamp substitution.
  * Support for custom date and time formatting in visible signature text.

* **Configurable output filename suffix**

  * Allows the output suffix to be selected directly from the interface.
  * Useful for document approval workflows requiring different signature states or signers.

## Custom timestamp formatting

Visible signature text supports custom date and time formatting.

The original timestamp placeholder remains available:

```text
${timestamp}
```

A custom format can be specified after a colon:

```text
${timestamp:yyyy.MM.dd}
```

Example output:

```text
2026.08.13
```

Other examples:

```text
${timestamp:dd.MM.yyyy}
${timestamp:yyyy-MM-dd}
${timestamp:dd/MM/yyyy HH:mm}
${timestamp:yyyy-MM-dd HH:mm:ss}
```

The format follows Java date/time pattern conventions.

Common pattern letters:

* `yyyy` — four-digit year
* `MM` — month
* `dd` — day of month
* `HH` — hour in 24-hour format (00–23)
* `mm` — minutes
* `ss` — seconds

> **Note:** `MM` means month, while `mm` means minutes.

Using a custom format changes only the visible representation of the timestamp. The digital signature and its cryptographic timestamping mechanisms remain independent of this display format.

## Project status

JSignPdf Tools is under active development.

The current code is based on the JSignPdf 3.1.x codebase. New functionality is developed in the `main` branch while the original JSignPdf repository is retained as the upstream source for future synchronization.

## Upstream project

JSignPdf is an open-source Java desktop application for digitally signing PDF documents.

Official project:

https://github.com/intoolswetrust/jsignpdf

Official website:

https://jsignpdf.eu/

JSignPdf supports, among other features:

* PKCS#12 software certificates
* PKCS#11 hardware tokens and smartcards
* RFC 3161 timestamping
* OCSP and CRL information
* Visible PDF signatures
* OpenPDF and PAdES signing engines
* Command-line and batch signing

## Building from source

JSignPdf Tools currently follows the build requirements of the upstream JSignPdf project.

Requirements:

* Java 21
* Apache Maven

Build with:

```bash
mvn clean install
```

Generated artifacts are placed under:

```text
distribution/target/
```

## Repository structure

This repository preserves the original JSignPdf source tree and development history.

The Git configuration used during development is:

```text
origin    -> JSignPdf Tools repository
upstream  -> official JSignPdf repository
```

This allows upstream JSignPdf changes to be incorporated while keeping JSignPdf Tools development separate.

## License

JSignPdf Tools is derived from JSignPdf and retains the licensing terms of the original project.

The source code is dual-licensed under:

* Mozilla Public License 2.0 (MPL 2.0)
* GNU Lesser General Public License 2.1 (LGPL 2.1)

See [License.md](License.md) for the complete license information.

## Credits

JSignPdf Tools is based on the work of the JSignPdf project and its contributors.

Original project:

**JSignPdf — intoolswetrust/jsignpdf**

This repository contains modifications and extensions developed for JSignPdf Tools.
