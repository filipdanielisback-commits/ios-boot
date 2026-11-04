# Device research matrix

All devices are **not yet validated**. No boot, driver, or feature support is claimed.

## Preliminary hardware identity research

These are research leads from public references, not confirmation of the physical handsets owned or targeted. Confirm the full model number shown by each actual device before treating a row as applicable.

| Target | Known model identifiers | Likely codename | SoC / GPU | Research status |
|---|---|---|---|---|
| Motorola Moto G60 | XT2135-1; XT2135-2 is listed as Moto G60 Vision by Motorola support | `hanoip` (shared device family with Moto G40 Fusion) | Snapdragon 732G / Adreno 618 | Provisional; exact variant needed |
| Redmi Note 13 Pro 5G | 2312DRA50G (Global); 2312DRA50C (China) | `garnet` | Snapdragon 7s Gen 2 / Adreno 710 | Provisional; confirm region/model |
| POCO X5 Pro 5G | 22101320G (Global); 22101320I (India) | `redwood` | Snapdragon 778G / Adreno 642L | Provisional; confirm region/model |
| Redmi Note 10 Pro | M2101K6G (Global); M2101K6T (Thailand); M2101K6R (Japan); India M2101K6P is commonly identified as `sweetin`; M2101K6I is Note 10 Pro Max India | `sweet` for global family; `sweetin` for India family | Snapdragon 732G / Adreno 618 for the 4G Pro family | Provisional; exact variant needed |

### Important variant warnings

- The Moto G60 codename `hanoip` is also used by the Moto G40 Fusion device family. Do not assume every shared device-tree entry means every hardware variant is identical.
- Redmi Note 13 Pro **5G** (`garnet`) is not the same target as the Redmi Note 13 Pro 4G or Redmi Note 13 Pro+.
- POCO X5 Pro 5G (`redwood`) is not the POCO X5 5G (`moonstone`).
- Redmi Note 10 Pro India variants use the `sweetin` family, while the global/other regional 4G Pro variants use `sweet`. The China Redmi Note 10 Pro 5G (`chopin`) is a different device and must not be mixed into this row.

## Public reference leads

- Motorola support lists XT2135-1 as Moto G60 and XT2135-2 as Moto G60 Vision: https://en-gb.support.motorola.com/app/answers/detail/a_id/167829/~/declarations-of-conformity
- Motorola G40 Fusion/G60 device-tree reference identifies `hanoip` and Snapdragon 732G: https://github.com/bhawesh2002/android_device_motorola_hanoip
- Redmi Note 13 Pro 5G model identifiers, `garnet`, and Snapdragon 7s Gen 2: https://www.deviceinfo.app/devices/redmi/note-13-pro-5g/
- POCO X5 Pro 5G official specifications identify Snapdragon 778G and Adreno 642L: https://www.po.co/global/product/poco-x5-pro-5g/specs/
- POCO X5 Pro 5G model identifiers and `redwood`: https://miuirom.org/phones/poco-x5-pro-5g
- Xiaomi's Redmi Note 10 Pro specifications identify Snapdragon 732G and Adreno 618: https://www.mi.com/global/product/redmi-note-10-pro/specs/
- Xiaomi model-family mapping for Redmi Note 10 Pro regional variants: https://github.com/KHwang9883/MobileModels/blob/master/brands/xiaomi_en.md

## What we still need from each actual phone

For each handset, record the full model number from **Settings → About phone** (or the model label in its regulatory information). Also record the marketed device name and region if shown. Do not post IMEI, serial number, phone number, account details, or other unique identifiers.

The actual model number is the deciding evidence. A codename inferred from the retail name alone is not enough to select a kernel tree or device configuration.

## Per-device checklist

Complete this independently for every exact model variant.

- [ ] Confirm commercial model and full model number from the actual device.
- [ ] Confirm codename, SoC, board identifier, and hardware revision against device-specific sources.
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
