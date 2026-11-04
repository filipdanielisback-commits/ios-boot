# Architecture and technical boundaries

## Intended layers

1. **Boot environment** — device-specific boot firmware, bootloader state, and a documented hand-off into experimental code.
2. **XNU kernel** — a target-specific configuration built from an identified public source revision.
3. **Hardware adaptation** — platform code, device trees, interrupt/timer support, storage, display, input, power, and other drivers.
4. **Darwin userspace** — user-space components that are independently available and legally usable.
5. **iOS frameworks and applications** — a separate and substantially larger compatibility and availability problem.
6. **Independent diagnostic interface** — optional tools written by this project; these must never be represented as Apple's iOS interface or genuine iOS apps.

## Important boundary

Public XNU source is not a complete iOS release. It does not by itself provide the complete iOS userspace, private frameworks, device firmware, proprietary drivers, Apple's full signing/boot chain, or the complete platform integration needed for iOS 26.

Therefore:
- A successful XNU compilation is only a build result.
- A kernel starting on hardware is only a kernel bring-up result.
- A Darwin shell is not the iOS application environment.
- An independently written launcher or interface is not iOS.
- No genuine iOS 26 claim is valid without evidence for the actual iOS userspace and platform stack.

## Suggested source layout

```
docs/       project status, architecture, device records
xnu/        source references and project-owned build configuration
platform/   device-specific research and adaptation
tools/      reproducible build and inspection tools
tests/      non-destructive tests and evidence collection
```

Do not add empty directories merely to imply implementation. Do not commit proprietary Apple files, firmware dumps, private keys, or extracted system images.

## Device separation

Keep configuration, build outputs, and evidence isolated per exact device variant. Shared code may be used only after compatibility is demonstrated and documented.

## Wi-Fi

Wi-Fi is disabled by default. It must not be enabled in a release before **2026-12-01**. A later change requires explicit review and device-specific validation.

## Development and testing principles

- Prefer source review, static analysis, reproducible builds, emulation, and non-destructive tests.
- Record toolchain versions and immutable source revisions.
- Preserve original device data; do not treat experimental images as daily-use software.
- Do not publish flashing procedures or claim a device is safe to flash without validated recovery and device-specific evidence.
