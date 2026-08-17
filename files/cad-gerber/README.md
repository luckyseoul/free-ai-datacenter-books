# OCP / OpenPOWER Gerbers and board files

NVIDIA does **not** publish NVLink, NVSwitch, or GB200 compute-tray Gerbers. These are the open packs we found.

## In this folder

| File | Origin | Contents |
|------|--------|----------|
| `Catalina-DC-SCM-artwork-OCP.zip` | [ocp-server-catalina-compute-tray](https://github.com/opencomputeproject/ocp-server-catalina-compute-tray) `03_DC-SCM/…/01_PCB manufacturing files/` | Allegro artwork: `top.art`, `bot.art`, `in1–4.art`, `gnd*.art`, `vcc*.art`, soldermask/paste/silkscreen, `*.drl`, `*.rou`, IPC-356 |
| `Barreleye-G2-SXM2-RISER-EVT-HW-GBR.tgz` | [zaius-barreleye-g2](https://github.com/opencomputeproject/zaius-barreleye-g2) `HW/EE/GBR/` | EVT CAM job for the **SXM2 GPU riser** (NVLink-era mezzanine on OpenPOWER Barreleye G2) |

## Upstream (not copied)

- **Full Catalina tray** — same repo: PDB, FIO, OSFP carrier, NVMe E1.S backplane, mechanical 3D CAD, BOM, stackup, schematics.
- **Zaius/Barreleye other GBR zips** — `HW/EE/GBR/*.zip` are Git LFS pointers (133 B). Run `git lfs pull` in that repo. Also `HW/EE/BRD`, `HW/EE/SCH`, `HW/ME`.
- **Project Olympus** — `HW/ProjectOlympus{Chassis,ComputeServer,UniversalMotherboard}20170410.7z` (16–20 MB). Extra mech zips on `files.opencompute.org` (see that repo’s `HW/README.md`).
- **OAI OAM/UBB** — specs only, [OCP-SVR-OAI-Open_Accelerator_Infrastructure](https://github.com/opencomputeproject/OCP-SVR-OAI-Open_Accelerator_Infrastructure).
- **OCP contributions DB** — [opencompute.org/contributions](https://www.opencompute.org/contributions).
