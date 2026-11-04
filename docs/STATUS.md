# Project status

**Last reviewed:** 2026-11-04  
**Overall state:** feasibility and planning  
**Verified iOS 26 boot:** none  
**Verified XNU boot on target devices:** none recorded

## Milestones

| Milestone | State | Evidence required |
|---|---|---|
| Define legal and technical scope | In progress | Documented source and redistribution boundaries |
| Identify exact hardware variants | Not started | Model number, codename, SoC, board/revision |
| Inventory public source trees | Not started | Upstream URLs, revisions, licenses |
| Study device boot environment | Not started | Device-specific documentation and source references |
| Establish reproducible build environment | Not started | Build scripts, toolchain versions, checksums |
| Build a target-specific XNU configuration | Not started | Configuration and complete build logs |
| Demonstrate XNU kernel boot | Not started | Serial/console logs tied to exact hardware |
| Demonstrate Darwin userspace | Not started | Reproducible userspace boot evidence |
| Evaluate genuine iOS userspace feasibility | Not started | Legal, technical, and dependency analysis |
| Validate device peripherals | Not started | Per-device test logs and explicit pass/fail results |

## Evidence policy

Every claimed result must record:

1. Exact commercial model and model number.
2. Device codename, SoC, board identifier, and relevant revision.
3. Source repository and immutable revision/commit.
4. Toolchain and build configuration.
5. Test method and expected result.
6. Raw logs or other reviewable evidence.
7. Known limitations and whether the result was independently reproduced.

A result on one device must not be copied to another device's status.

## Wi-Fi policy

Wi-Fi remains disabled by default. No release before **2026-12-01** may enable Wi-Fi. Any later proposal requires explicit review, device-specific testing, and documented results.

## Immediate research tasks

- Identify and document each target's exact hardware variants.
- Locate authoritative public kernel/device-tree sources and record their licenses.
- Map the publicly available XNU components against the requirements of each target.
- Document boot-chain and driver gaps without claiming unsupported functionality.
- Define a reproducible, non-destructive build and test workflow.
