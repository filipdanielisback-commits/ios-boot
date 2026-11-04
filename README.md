# ios-boot

Research into whether an iOS 26-era Darwin/XNU system can be brought up on selected Android phones.

> **Status: feasibility and architecture research.** This repository does not currently claim that iOS 26, its userspace, or even an XNU kernel has been booted on any listed device.

## Research targets

- Motorola Moto G60
- Xiaomi Redmi Note 13 Pro 5G
- POCO X5 Pro 5G
- Xiaomi Redmi Note 10 Pro

Exact model variants, codenames, SoCs, and board revisions must be recorded separately. Results for one variant or device must not be assumed to apply to another.

## What “genuine iOS” means here

The long-term research question is whether a genuine Apple iOS userspace can run on these devices. A public XNU kernel build, a Darwin command-line environment, a simulator, or an independently written iOS-like interface is **not** a genuine iOS 26 boot.

Apple's public source releases cover parts of the Darwin/XNU stack, not the complete iOS 26 operating system. iOS also depends on proprietary userspace components, frameworks, firmware, signing and boot-chain mechanisms, and device-specific drivers. This project will not claim those components are available merely because XNU source is public.

No Apple proprietary binaries, firmware, private frameworks, or extracted system images may be committed or redistributed here. Any independently developed interface or fallback environment must be clearly labelled as independent software, never as genuine iOS.

## Project rules

- Report only results that have reproducible logs or other verifiable evidence.
- Distinguish **planned**, **implemented**, **built**, **boot-tested**, and **verified** work.
- Record exact device variant and source/build identifiers for every result.
- Do not fabricate support, screenshots, benchmark results, or boot claims.
- Keep Wi-Fi disabled by default. Do not enable it in a release before **2026-12-01**; any later change requires explicit review and testing.
- Prefer source inspection, reproducible builds, emulators, and non-destructive tests.
- Do not treat experimental images as suitable for a primary phone.

## Documentation

- [Project status](docs/STATUS.md)
- [Architecture and technical boundaries](docs/ARCHITECTURE.md)
- [Device research matrix](docs/DEVICE-MATRIX.md)

## What counts as progress

A milestone should include the exact hardware identity, source provenance, build configuration, test procedure, logs, observed result, and known limitations. A successful kernel build is not a successful device boot; a kernel boot is not a complete Darwin userspace; and neither alone demonstrates genuine iOS 26.

## Disclaimer

This is an independent experimental research project and is not affiliated with, endorsed by, or supported by Apple. “iOS” and Apple product names are used only to describe the research target.
