# Device research matrix

All four devices remain project targets. The maintainer currently has physical access only to the Moto G60 Vision XT2135-2; the other three are community/remote-validation targets until test hardware or volunteer testers are available. No iOS/XNU boot, driver, or feature support is claimed for any device.

## Hardware access and validation

| Device | Physical access for this project | What can be done now | What must wait for device testing |
|---|---|---|---|
| Moto G60 Vision XT2135-2 | Available to maintainer; user reports original Motorola Android software (stock ROM) | Record Android/build fingerprint and inspect read-only device properties; research sources | Any boot or hardware-support claim still needs evidence |
| Redmi Note 13 Pro 5G | Not currently available | Source research, configuration design, build analysis | Hardware bring-up, boot tests, peripheral validation |
| POCO X5 Pro 5G | Not currently available | Source research, configuration design, build analysis | Hardware bring-up, boot tests, peripheral validation |
| Redmi Note 10 Pro | Not currently available | Source research, configuration design, build analysis | Hardware bring-up, boot tests, peripheral validation |

A project target is not the same as a supported device. For devices without local hardware, mark work as **research-only** until a volunteer with the exact model can run and share reproducible tests. Never mark such a device boot-tested or verified based only on source availability or another device's results.

## Preliminary hardware identity research

These are research leads from public references, not confirmation of the physical handsets owned or targeted. Confirm the full model number shown by each actual device before treating a row as applicable.

| Target | Known model identifiers | Likely codename | SoC / GPU | Research status |
|---|---|---|---|---|
| Motorola Moto G60 (user-confirmed XT2135-2) | **XT2135-2**; Motorola's EU declaration labels it **moto g60 vision** (type MC38C) | `hanoip` (device-family lead; confirm against on-device build properties) | Snapdragon 732G / Adreno 618 (provisional) | Model confirmed; platform details provisional |
| Redmi Note 13 Pro 5G | 2312DRA50G (Global); 2312DRA50C (China) | `garnet` | Snapdragon 7s Gen 2 / Adreno 710 | Provisional; confirm region/model |
| POCO X5 Pro 5G | 22101320G (Global); 22101320I (India) | `redwood` | Snapdragon 778G / Adreno 642L | Provisional; confirm region/model |
| Redmi Note 10 Pro | M2101K6G (Global); M2101K6T (Thailand); M2101K6R (Japan); India M2101K6P is commonly identified as `sweetin`; M2101K6I is Note 10 Pro Max India | `sweet` for global family; `sweetin` for India family | Snapdragon 732G / Adreno 618 for the 4G Pro family | Provisional; exact variant needed |

### Important variant warnings

- The Moto G60 codename `hanoip` is also used by the Moto G40 Fusion device family. Do not assume every shared device-tree entry means every hardware variant is identical.
- Redmi Note 13 Pro **5G** (`garnet`) is not the same target as the Redmi Note 13 Pro 4G or Redmi Note 13 Pro+.
- POCO X5 Pro 5G (`redwood`) is not the POCO X5 5G (`moonstone`).
- Redmi Note 10 Pro India variants use the `sweetin` family, while the global/other regional 4G Pro variants use `sweet`. The China Redmi Note 10 Pro 5G (`chopin`) is a different device and must not be mixed into this row.

## Public reference leads

Xiaomi's public kernel-source index lists device branches for `garnet` (Redmi Note 13 Pro), `redwood` (POCO X5 Pro 5G), and `sweet` (Redmi Note 10 Pro). These are Android kernel source leads, not ready-made XNU ports and not proof of iOS compatibility: [Xiaomi kernel source mirror](https://gitlab.com/MiCode-mirror/xiaomi_kernel_opensource). The `redwood-s-oss` branch explicitly lists POCO X5 Pro 5G; `sweet-r-oss` lists Redmi Note 10 Pro. [Source index details](https://gitextract.com/MiCode/Xiaomi_Kernel_OpenSource).

- Motorola support lists XT2135-1 as Moto G60 and XT2135-2 as Moto G60 Vision: https://en-gb.support.motorola.com/app/answers/detail/a_id/167829/~/declarations-of-conformity
- Motorola G40 Fusion/G60 device-tree reference identifies `hanoip` and Snapdragon 732G: https://github.com/bhawesh2002/android_device_motorola_hanoip
- Redmi Note 13 Pro 5G model identifiers, `garnet`, and Snapdragon 7s Gen 2: https://www.deviceinfo.app/devices/redmi/note-13-pro-5g/
- POCO X5 Pro 5G official specifications identify Snapdragon 778G and Adreno 642L: https://www.po.co/global/product/poco-x5-pro-5g/specs/
- POCO X5 Pro 5G model identifiers and `redwood`: https://miuirom.org/phones/poco-x5-pro-5g
- Xiaomi's Redmi Note 10 Pro specifications identify Snapdragon 732G and Adreno 618: https://www.mi.com/global/product/redmi-note-10-pro/specs/
- Xiaomi model-family mapping for Redmi Note 10 Pro regional variants: https://github.com/KHwang9883/MobileModels/blob/master/brands/xiaomi_en.md

## What we still need from each actual phone

For each handset, record the full model number from **Settings → About phone** (or the model label in its regulatory information). Also record the marketed device name and region if shown. Do not post IMEI, serial number, phone number, account details, or other unique identifiers.

The actual model number is the deciding evidence. Moto G60 XT2135-2 is distinguished here from XT2135-1; Motorola's own support listing calls XT2135-2 the moto g60 vision, while XT2135-1 is listed as moto g60. The `hanoip` codename and Snapdragon 732G/Adreno 618 identification remain research leads to verify against the actual device's build properties and authoritative source trees. A codename inferred from the retail name alone is not enough to select a kernel tree or device configuration.

## Moto G60 Vision baseline capture

Before any development work, record the following from the stock system. Do not share IMEI, serial number, phone number, account details, or other unique identifiers.

- [ ] Android version.
- [ ] Full software/build number.
- [ ] Android security update date.
- [ ] Build fingerprint (review for personal identifiers before sharing).
- [ ] Kernel version as displayed in Settings, if available.
- [ ] Confirm model remains XT2135-2.

Initial inspection should be read-only. No bootloader unlocking, flashing, partition writes, firmware replacement, or factory reset is part of this baseline step.

## Per-device checklist

Complete this independently for every exact model variant.

- [x] Moto G60: user confirmed model number XT2135-2. Motorola's regulatory declaration identifies this SKU as moto g60 vision, type MC38C. [Official declaration](https://en-us.support.motorola.com/ci/fattach/get/79315385/1664922506/redirect/1/filename/XT2135-2_Moto%2BG60%2BVision%2BMC38C%2BRED%2BDoC.pdf)
- [ ] Confirm the remaining devices' commercial model and full model numbers from the actual devices.
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
