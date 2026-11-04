# Device research matrix

All devices are **not yet validated**. No boot, driver, or feature support is claimed.

| Target | Exact variant/codename | SoC / board | Research status |
|---|---|---|---|
| Motorola Moto G60 | To identify | To identify | Not started |
| Redmi Note 13 Pro 5G | To identify | To identify | Not started |
| POCO X5 Pro 5G | To identify | To identify | Not started |
| Redmi Note 10 Pro | To identify | To identify | Not started |

## Per-device checklist

Complete this independently for every exact model variant.

- [ ] Record commercial model and full model number.
- [ ] Confirm codename, SoC, board identifier, and hardware revision.
- [ ] Record bootloader and boot-environment constraints from authoritative sources.
- [ ] Locate public kernel and device-tree sources; record immutable revisions and licenses.
- [ ] Identify memory map, interrupt controller, timers, storage, and console requirements.
- [ ] Research display and touchscreen interfaces.
- [ ] Research GPU and audio support.
- [ ] Research power management and battery reporting.
- [ ] Record Bluetooth support status.
- [ ] Keep Wi-Fi disabled under the project policy.
- [ ] Attach build/test logs and list unresolved blockers.

## Result vocabulary

Use precise labels:

- **Not started** — no investigation recorded.
- **Researching** — sources or requirements are being examined.
- **Built** — a reproducible build completed; this does not imply boot.
- **Boot-tested** — a test was performed on the exact hardware; attach logs.
- **Verified** — evidence meets the project policy and has been reviewed.

Do not infer a pass from another device in the same product family. A feature remains unverified until there is evidence for that exact variant.
