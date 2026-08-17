# AI datacenter catalog (2026-08-17 harvest)

Index of **free** books, vendor architecture PDFs, conference papers, OCP hardware (including Gerbers), and GitHub repos. Prefer a local `files/` path when we harvested a binary; otherwise the official URL.

This pass searched GitHub (including `opencomputeproject`), NVIDIA docs, Google Research, USENIX/arXiv, IEA, ASHRAE, OCP contribution trees, and vendor whitepaper hosts. NVIDIA **does not publish NVLink switch / GPU Gerbers**; the Gerber packs below are the closest open hardware (OCP DC-SCM + OpenPOWER SXM2 riser).

## NVLink generations

Official current numbers from [NVIDIA NVLink & NVLink Switch](https://www.nvidia.com/en-us/data-center/nvlink/) (crawled 2026-08-17). Earlier gens from the harvested architecture whitepapers and Li et al. 2019.

| Gen | GPU family | Bidirectional BW / GPU | Links / GPU | Scale-up domain | Local / source |
|-----|------------|------------------------|-------------|-----------------|----------------|
| 1 | Pascal P100 | 160 GB/s | 4 | GPU–GPU mesh | [`files/nvlink/pascal-architecture-whitepaper.pdf`](files/nvlink/pascal-architecture-whitepaper.pdf) |
| 2 | Volta V100 + first NVSwitch (DGX-2) | 300 GB/s | 6 | 16-GPU NVSwitch | [`files/nvlink/volta-architecture-whitepaper.pdf`](files/nvlink/volta-architecture-whitepaper.pdf) |
| 3 | Ampere A100 | 600 GB/s | 12 | 8-GPU NVSwitch | [`files/nvlink/ampere-architecture-whitepaper.pdf`](files/nvlink/ampere-architecture-whitepaper.pdf) |
| 4 | Hopper H100 / H200 | 900 GB/s | 18 | 8-GPU; GH200 NVLink Switch System up to 256 | [Hopper architecture page](https://www.nvidia.com/en-us/data-center/technologies/hopper-architecture/) · H100 SuperPOD RA below |
| 5 | Blackwell B200 / GB200 | 1,800 GB/s | 18 | 8-GPU or **NVL72** (130 TB/s aggregate) | [GB200 NVL72](https://www.nvidia.com/en-us/data-center/gb200-nvl72/) · GB200 SuperPOD RA below |
| 6 | Rubin / Vera Rubin NVL72 | 3,600 GB/s | 36 | 8-GPU or **NVL72** (260 TB/s aggregate) | [NVLink page](https://www.nvidia.com/en-us/data-center/nvlink/) · [Vera Rubin](https://www.nvidia.com/en-us/data-center/technologies/rubin/) |
| C2C | Grace–Hopper / Grace–Blackwell | chip-to-chip coherent | — | Superchip (CPU+GPU) | GB200 SuperPOD RA |

Also harvested:

- Turing architecture WP (consumer/pro viz; NVLink bridge era): [`files/nvlink/turing-architecture-whitepaper.pdf`](files/nvlink/turing-architecture-whitepaper.pdf)
- Measurement paper, NVLink 1/2 vs PCIe vs NV-SLI: [`files/papers/gpu-interconnect-eval-arxiv-1903.04611.pdf`](files/papers/gpu-interconnect-eval-arxiv-1903.04611.pdf) ([arXiv:1903.04611](https://arxiv.org/abs/1903.04611))
- Independent notes: [Glenn Klockwood NVLink garden](https://www.glennklockwood.com/garden/nvlink)

SXM2 pinout (community, not NVIDIA official): [xiaoyu9733/sxm2-pinout-definition](https://github.com/xiaoyu9733/sxm2-pinout-definition) — snapshot [`files/github-docs/sxm2-pinout-README.md`](files/github-docs/sxm2-pinout-README.md)

## SuperPOD / rack-scale reference architectures (harvested PDFs)

| Doc | Local file | Official HTML |
|-----|------------|---------------|
| DGX SuperPOD RA — H100 (RA-11333-001 V11, 2023-09-22) | [`files/superpod-ra/RA-DGX-H100-SuperPOD.pdf`](files/superpod-ra/RA-DGX-H100-SuperPOD.pdf) | [docs.nvidia.com …/h100](https://docs.nvidia.com/dgx-superpod/reference-architecture-scalable-infrastructure-h100/latest/) |
| DGX SuperPOD RA — B200 (RA-11334-001 V08, 2025-04-24) | [`files/superpod-ra/RA-DGX-B200-SuperPOD.pdf`](files/superpod-ra/RA-DGX-B200-SuperPOD.pdf) | [docs.nvidia.com …/b200](https://docs.nvidia.com/dgx-superpod/reference-architecture-scalable-infrastructure-b200/latest/) |
| DGX SuperPOD RA — GB200 NVL72 (RA-11338-001 V01, 2025-06-16) | [`files/superpod-ra/RA-DGX-GB200-SuperPOD.pdf`](files/superpod-ra/RA-DGX-GB200-SuperPOD.pdf) | [docs.nvidia.com …/gb200](https://docs.nvidia.com/dgx-superpod/reference-architecture-scalable-infrastructure-gb200/latest/) |

Related vendor / product pages (HTML, some PDF-gated):

- [DGX SuperPOD product](https://www.nvidia.com/en-us/data-center/dgx-superpod/)
- [DGX GB200 datasheet landing](https://resources.nvidia.com/en-us-dgx-systems/dgx-superpod-gb200-datasheet)
- [HGX platform](https://www.nvidia.com/en-us/data-center/hgx/) (HGX Rubin NVL8 / NVLink 6)
- [Enterprise Reference Architectures index](https://docs.nvidia.com/enterprise-reference-architectures/index.html) (Cisco / HPE / Lenovo HGX B300)
- [Spectrum-X white paper](https://resources.nvidia.com/en-us-networking-ai/nvidia-spectrum-x) (resources.nvidia.com gated)
- [800 VDC architecture](https://www.nvidia.com/en-us/data-center/technologies/800-vdc-architecture/) + [developer blog](https://developer.nvidia.com/blog/building-the-800-vdc-ecosystem-for-efficient-scalable-ai-factories/) + [whitepaper share link](https://nvdam.nvidia.com/assets/share/asset/zlg5snufeo)
- On-board 800→12.5 V conversion: [`files/energy-cooling/EPC-800VDC-to-12.5V.pdf`](files/energy-cooling/EPC-800VDC-to-12.5V.pdf)

## Gerbers, board files, mechanical CAD

NVIDIA NVLink / NVSwitch / GB200 compute-tray Gerbers are **not public**. Open hardware that *is* public:

### Harvested locally

| Pack | What it is | Local file |
|------|------------|------------|
| **Meta Catalina DC-SCM artwork** | Real PCB manufacturing Gerbers (`.art` layers, `.drl` drill, `.rou` route, IPC-356 netlist) for the Datacenter Secure Control Module on Meta’s Catalina ORv3 compute tray | [`files/cad-gerber/Catalina-DC-SCM-artwork-OCP.zip`](files/cad-gerber/Catalina-DC-SCM-artwork-OCP.zip) |
| **Barreleye G2 SXM2 riser** | OpenPOWER / OCP EVT CAM job for the **SXM2 GPU riser** (NVLink-era mezzanine). Genesis/CAM-350 style tree, not a simple RS-274X zip | [`files/cad-gerber/Barreleye-G2-SXM2-RISER-EVT-HW-GBR.tgz`](files/cad-gerber/Barreleye-G2-SXM2-RISER-EVT-HW-GBR.tgz) |

### Stay on GitHub / OCP (too large or LFS)

| Repo | Gerber / CAD path | Notes |
|------|-------------------|-------|
| [opencomputeproject/ocp-server-catalina-compute-tray](https://github.com/opencomputeproject/ocp-server-catalina-compute-tray) | `03_DC-SCM/…/04_Manufacturing Files/` plus `01_PDB`, `02_FIO`, `04_OSFP carrier board`, `05_NVMe E1.s backplane`, `06_mechanical chassis 3d cad file` | Full Meta Catalina compute tray: schematics, layout, BOM, stackup, 3D CAD. We only mirrored the DC-SCM artwork zip. |
| [opencomputeproject/zaius-barreleye-g2](https://github.com/opencomputeproject/zaius-barreleye-g2) | [`HW/EE/GBR/`](https://github.com/opencomputeproject/zaius-barreleye-g2/tree/master/HW/EE/GBR) | **SXM2 riser `.tgz` is a real blob.** Other `*-GBR-*.zip` files are **Git LFS pointers** (133 B). Also `HW/EE/BRD`, `HW/EE/SCH`, `HW/ME`, `HW/thermal`. |
| [opencomputeproject/Project_Olympus](https://github.com/opencomputeproject/Project_Olympus) | [`HW/`](https://github.com/opencomputeproject/Project_Olympus/tree/master/HW) `ProjectOlympus{Chassis,ComputeServer,UniversalMotherboard}20170410.7z` (16–20 MB each) | Microsoft Olympus board/mech packs. Extra mechanical zips on `files.opencompute.org` (see `HW/README.md`). |
| [opencomputeproject/OCP-SVR-OAI-Open_Accelerator_Infrastructure](https://github.com/opencomputeproject/OCP-SVR-OAI-Open_Accelerator_Infrastructure) | specs, not Gerbers | OAM / UBB / Expansion base specs (r1.0 → r2.0). Rack-scale AI has largely outgrown UBB. |
| [facebookarchive/opencompute](https://github.com/facebookarchive/opencompute) | historical CAD | Archived early Facebook OCP mechanicals. |
| [opencomputeproject/CADCloud](https://github.com/opencomputeproject/CADCloud) | CAD sharing infra | Not a design pack; hosting for CAD engineers. |

OCP contribution database (specs + many more design packages, login-light): [opencompute.org/contributions](https://www.opencompute.org/contributions)

## OCP AI cluster / rack / management (GitHub)

| Repo | Why it matters | Snapshot |
|------|----------------|----------|
| [OCP-OCDAI-training-fabric](https://github.com/opencomputeproject/OCP-OCDAI-training-fabric) | Open Cluster Designs AI **training** fabric: OPG-64…512 / XOC-256…1024, rail-optimized vs single-homed, SONiC/EVPN, NetBox inventories, draw.io | [`files/github-docs/OCP-OCDAI-training-fabric-README.md`](files/github-docs/OCP-OCDAI-training-fabric-README.md) |
| [OCP-OCDAI-inference-fabric](https://github.com/opencomputeproject/OCP-OCDAI-inference-fabric) | Companion **inference** fabric RA | [`files/github-docs/OCP-OCDAI-inference-fabric-README.md`](files/github-docs/OCP-OCDAI-inference-fabric-README.md) |
| [OCP-SVR-OAI-Open_Accelerator_Infrastructure](https://github.com/opencomputeproject/OCP-SVR-OAI-Open_Accelerator_Infrastructure) | OAM + UBB + Exp specs; 2024 note that rack-scale NVLink domains superseded UBB | [`files/github-docs/OCP-OAI-README.md`](files/github-docs/OCP-OAI-README.md) |
| [ocp-server-catalina-compute-tray](https://github.com/opencomputeproject/ocp-server-catalina-compute-tray) | Meta Catalina ORv3 tray (DC-SCM Gerbers above) | — |
| [ocp-server-rmc-tray](https://github.com/opencomputeproject/ocp-server-rmc-tray) | Rack Management Controller tray | — |
| [HWMgmt-Module-DCSCM-LTPI](https://github.com/opencomputeproject/HWMgmt-Module-DCSCM-LTPI) | DC-SCM 2.x LTPI SystemVerilog reference | [`files/github-docs/OCP-DCSCM-LTPI-README.md`](files/github-docs/OCP-DCSCM-LTPI-README.md) |
| [ocp-hm-system-gpu-management](https://github.com/opencomputeproject/ocp-hm-system-gpu-management) | GPU management profiles | — |
| [OCP-RP-Rack-and-Power](https://github.com/opencomputeproject/OCP-RP-Rack-and-Power) | Rack & Power project repo | — |
| [Project_Olympus](https://github.com/opencomputeproject/Project_Olympus) | Microsoft open cloud server | [`files/github-docs/OCP-Project-Olympus-README.md`](files/github-docs/OCP-Project-Olympus-README.md) |
| [zaius-barreleye-g2](https://github.com/opencomputeproject/zaius-barreleye-g2) | OpenPOWER POWER9 + SXM2 | [`files/github-docs/OCP-zaius-barreleye-g2-README.md`](files/github-docs/OCP-zaius-barreleye-g2-README.md) |
| [onie](https://github.com/opencomputeproject/onie) / [SAI](https://github.com/opencomputeproject/SAI) / [OpenNetworkLinux](https://github.com/opencomputeproject/OpenNetworkLinux) | Bare-metal switch install / SAI / ONL | — |
| [ODSA-BoW](https://github.com/opencomputeproject/ODSA-BoW) | Bunch-of-Wires die-to-die (chiplet, not rack) | — |
| [OCP-Security-SAFE](https://github.com/opencomputeproject/OCP-Security-SAFE) | Datacenter product security reviews | — |

ORv3 context: [Meta OCP Summit 2022 / Grand Teton](https://engineering.fb.com/2022/10/18/open-source/ocp-summit-2022-grand-teton/), [Eaton ORv3](https://www.eaton.com/us/en-us/catalog/backup-power-ups-surge-it-power-distribution/eaton-intelligent-power-manager/power-management-alliance-partners/open-compute-project.html).

## Datacenter / AI-cluster papers (harvested)

| Paper | Local file |
|-------|------------|
| Google Jupiter Rising (SIGCOMM’15) | [`files/papers/google-jupiter-rising.pdf`](files/papers/google-jupiter-rising.pdf) |
| Google Jupiter Evolving — OCS + SDN (SIGCOMM’22) | [`files/papers/jupiter-evolving-sigcomm22.pdf`](files/papers/jupiter-evolving-sigcomm22.pdf) ([Google storage](https://storage.googleapis.com/gweb-research2023-media/pubtools/6752.pdf)) |
| Google Aquila (NSDI’22) | [`files/papers/aquila-nsdi22.pdf`](files/papers/aquila-nsdi22.pdf) |
| ByteDance MegaScale — 10k+ GPU training (NSDI’24) | [`files/papers/megascale-nsdi24.pdf`](files/papers/megascale-nsdi24.pdf) |
| Rail-only fabric (arXiv:2307.12169) — cites GB200 NVL72 | [`files/papers/rail-only-arxiv-2307.12169.pdf`](files/papers/rail-only-arxiv-2307.12169.pdf) |
| RailX (arXiv:2507.18889) | [`files/papers/railx-arxiv-2507.18889.pdf`](files/papers/railx-arxiv-2507.18889.pdf) |
| MixNet optical-electrical MoE fabric (arXiv:2501.03905 / SIGCOMM’25) | [`files/papers/mixnet-arxiv-2501.03905.pdf`](files/papers/mixnet-arxiv-2501.03905.pdf) |
| TPU v4 (arXiv:2304.01433 / ISCA’23) | [`files/papers/tpu-v4-isca23.pdf`](files/papers/tpu-v4-isca23.pdf) |
| Li et al. GPU interconnect eval (arXiv:1903.04611) | [`files/papers/gpu-interconnect-eval-arxiv-1903.04611.pdf`](files/papers/gpu-interconnect-eval-arxiv-1903.04611.pdf) |
| Generating datacenter configs incl. IT/power/cooling (arXiv:2604.09616) | [`files/papers/generating-datacenter-configs-arxiv-2604.09616.pdf`](files/papers/generating-datacenter-configs-arxiv-2604.09616.pdf) |

ACM-gated (no free PDF this pass — use author copies / ACM Open):

- Alibaba **HPN** (SIGCOMM’24) — [DOI 10.1145/3651890.3672265](https://dl.acm.org/doi/10.1145/3651890.3672265)
- Meta **RDMA over Ethernet for Distributed Training** (SIGCOMM’24)
- Google Lightwave Fabrics / related OCS follow-ons

## Energy, power, cooling

| Resource | Local / URL |
|----------|-------------|
| IEA *Energy and AI* (Apr 2025) | [`files/energy-cooling/IEA-Energy-and-AI-2025.pdf`](files/energy-cooling/IEA-Energy-and-AI-2025.pdf) |
| IEA *Key Questions on Energy and AI* (Apr 2026) | [`files/energy-cooling/IEA-Key-Questions-on-Energy-and-AI-2026.pdf`](files/energy-cooling/IEA-Key-Questions-on-Energy-and-AI-2026.pdf) |
| FEMP Best Practices 2024 | [`files/energy-cooling/FEMP-Best-Practices-Data-Center-Design-2024.pdf`](files/energy-cooling/FEMP-Best-Practices-Data-Center-Design-2024.pdf) |
| LBNL/FEMP historical | [`files/energy-cooling/LBNL-FEMP-Best-Practices.pdf`](files/energy-cooling/LBNL-FEMP-Best-Practices.pdf) |
| ASHRAE TC 9.9 power-equipment thermal WP | [`files/energy-cooling/ASHRAE-TC99-Power-Equipment-Thermal-Guidelines.pdf`](files/energy-cooling/ASHRAE-TC99-Power-Equipment-Thermal-Guidelines.pdf) |
| ASHRAE TC 9.9 storage thermal WP | [`files/energy-cooling/ASHRAE-TC99-Storage-Thermal-Guidelines.pdf`](files/energy-cooling/ASHRAE-TC99-Storage-Thermal-Guidelines.pdf) |
| ASHRAE AI datacenter framework (HTML + Datacom Encyclopedia) | [ashrae.org …/ai-data-center-framework](https://www.ashrae.org/technical-resources/ai-data-center-framework/tools-standards-and-resources) |
| ASHRAE Datacom Series (paid encyclopedia; historical book PDFs inside) | [datacom.ashrae.org](https://datacom.ashrae.org/) |
| EPC 800 VDC → 12.5 V | [`files/energy-cooling/EPC-800VDC-to-12.5V.pdf`](files/energy-cooling/EPC-800VDC-to-12.5V.pdf) |

## GitHub catalogs and tooling (not already in `software-docs/`)

| Repo | Stars (this search) | Snapshot |
|------|---------------------|----------|
| [trevor-vincent/awesome-high-performance-computing](https://github.com/trevor-vincent/awesome-high-performance-computing) | 1309 | [`files/github-docs/awesome-hpc-README.md`](files/github-docs/awesome-hpc-README.md) |
| [goabiaryan/awesome-gpu-engineering](https://github.com/goabiaryan/awesome-gpu-engineering) | 585 | [`files/github-docs/awesome-gpu-engineering-README.md`](files/github-docs/awesome-gpu-engineering-README.md) |
| [LonghornSilicon/awesome-ai-accelerators](https://github.com/LonghornSilicon/awesome-ai-accelerators) | 156 | [`files/github-docs/awesome-ai-accelerators-README.md`](files/github-docs/awesome-ai-accelerators-README.md) |
| [Shashank-Tripathi-07/awesome-ml-systems-engineering](https://github.com/Shashank-Tripathi-07/awesome-ml-systems-engineering) | 26 | [`files/github-docs/awesome-ml-systems-engineering-README.md`](files/github-docs/awesome-ml-systems-engineering-README.md) |
| [gurrakeller/AI-Infrastructure-Solutions-Architecture](https://github.com/gurrakeller/AI-Infrastructure-Solutions-Architecture) | 7 | [`files/github-docs/AI-Infrastructure-Solutions-Architecture-README.md`](files/github-docs/AI-Infrastructure-Solutions-Architecture-README.md) |
| [SemiAnalysisAI/InferenceX](https://github.com/SemiAnalysisAI/InferenceX) | 1396 | GB200 NVL72 vs MI355X vs B200 vs GB300 live bench — [`files/github-docs/SemiAnalysis-InferenceX-README.md`](files/github-docs/SemiAnalysis-InferenceX-README.md) |
| [NVIDIA/topograph](https://github.com/NVIDIA/topograph) | 156 | NVLink / IB topology discovery — [`files/github-docs/NVIDIA-topograph-README.md`](files/github-docs/NVIDIA-topograph-README.md) |
| [NVIDIA/Fabric-Manager-Client](https://github.com/NVIDIA/Fabric-Manager-Client) | 18 | Shared NVSwitch partitions — [`files/github-docs/NVIDIA-Fabric-Manager-Client-README.md`](files/github-docs/NVIDIA-Fabric-Manager-Client-README.md) |
| [DeepLink-org/superpod-whitepaper](https://github.com/DeepLink-org/superpod-whitepaper) | 70 | Chinese SuperPod / distributed-inference WP (MkDocs) — [`files/github-docs/DeepLink-superpod-whitepaper-README.md`](files/github-docs/DeepLink-superpod-whitepaper-README.md) |
| [uuudown/Tartan](https://github.com/uuudown/Tartan) | 72 | Multi-GPU interconnect benchmark (NVLink vs PCIe) | — |
| [c3sr/comm_scope](https://github.com/c3sr/comm_scope) | 28 | NUMA-aware multi-GPU transfer benches | — |

Already snapshotted in this repo: llama.cpp, vLLM, Ollama, LocalAI, transformers, OpenHands, firecrawl, crawl4ai, browser-use, markitdown.

## Reverse-engineered microarchitecture (CPU / GPU / NPU / TPU)

Unofficial. Encoding tables and latencies can be wrong or generation-specific. NVIDIA SASS, Apple AMX/ANE/AGX, and Qualcomm Hexagon have **no public vendor ISA** for the interesting parts; these are the best public reconstructions.

### NVIDIA SASS / SM (community)

| Artifact | What it reconstructs | Local / URL |
|----------|----------------------|-------------|
| Jia et al. *Dissecting Volta* (arXiv:1804.06826) | Volta SASS encoding, schedulers, L0/L1, Tensor Core | [`files/reverse-eng/dissecting-volta-arxiv-1804.06826.pdf`](files/reverse-eng/dissecting-volta-arxiv-1804.06826.pdf) |
| Jia et al. *Dissecting Turing T4* (arXiv:1903.07486) | Turing vs prior gens, new ops | [`files/reverse-eng/dissecting-turing-t4-arxiv-1903.07486.pdf`](files/reverse-eng/dissecting-turing-t4-arxiv-1903.07486.pdf) |
| Abdelkhalik et al. *Demystifying Ampere* (arXiv:2208.11174) | A100 CPI / ISA / Tensor Core | [`files/reverse-eng/demystifying-ampere-arxiv-2208.11174.pdf`](files/reverse-eng/demystifying-ampere-arxiv-2208.11174.pdf) |
| Luo et al. *Benchmarking Hopper* (arXiv:2402.13499) | Hopper vs Ada vs Ampere + new ISA/APIs | [`files/reverse-eng/dissecting-hopper-arxiv-2402.13499.pdf`](files/reverse-eng/dissecting-hopper-arxiv-2402.13499.pdf) |
| Luo et al. *Hopper multilevel* (arXiv:2501.12084) | Follow-on multi-level Hopper analysis | [`files/reverse-eng/dissecting-hopper-multilevel-arxiv-2501.12084.pdf`](files/reverse-eng/dissecting-hopper-multilevel-arxiv-2501.12084.pdf) |
| Sun et al. *Dissecting Tensor Cores* (arXiv:2206.02874) | Turing/Ampere MMA latency/throughput/numerics | [`files/reverse-eng/dissecting-tensor-cores-arxiv-2206.02874.pdf`](files/reverse-eng/dissecting-tensor-cores-arxiv-2206.02874.pdf) |
| [cloudcores/CuAssembler](https://github.com/cloudcores/CuAssembler) | Unofficial assembler for many SASS gens | [`files/github-docs/CuAssembler-README.md`](files/github-docs/CuAssembler-README.md) |
| [NervanaSystems/maxas](https://github.com/NervanaSystems/maxas) | Maxwell SASS assembler (Scott Gray; archived) | [`files/github-docs/maxas-README.md`](files/github-docs/maxas-README.md) |
| [daadaada/turingas](https://github.com/daadaada/turingas) | Volta/Turing assembler | [`files/github-docs/turingas-README.md`](files/github-docs/turingas-README.md) |
| [florianmattana/sass-king](https://github.com/florianmattana/sass-king) | SM120/Blackwell SASS dictionary + Tensor Core corpus | [`files/github-docs/sass-king-README.md`](files/github-docs/sass-king-README.md) |
| [kacper-daftcode/blackwell-isa](https://github.com/kacper-daftcode/blackwell-isa) | SM120 machine-readable ISA (`sm120.json`) + [HTML ref](https://kacper-daftcode.github.io/blackwell-isa/SM120_ISA_REFERENCE.html) | [`files/github-docs/blackwell-isa-README.md`](files/github-docs/blackwell-isa-README.md) |
| [envytools/envytools](https://github.com/envytools/envytools) | Classic Nouveau-era NVIDIA HW RE toolkit (MMIO, falcon, older ISA) | — |
| [HPMLL/NVIDIA-Hopper-Benchmark](https://github.com/HPMLL/NVIDIA-Hopper-Benchmark) | Code for the Luo Hopper papers | [`files/github-docs/Hopper-Benchmark-README.md`](files/github-docs/Hopper-Benchmark-README.md) |

Vendor-released (not RE, but the only official chip-interface docs):

- [NVIDIA/open-gpu-doc](https://github.com/NVIDIA/open-gpu-doc) — class methods, BIOS tables, display/devinit ([github pages](https://nvidia.github.io/open-gpu-doc/)) — [`files/github-docs/NVIDIA-open-gpu-doc-README.md`](files/github-docs/NVIDIA-open-gpu-doc-README.md)
- [NVIDIA/open-gpu-kernel-modules](https://github.com/NVIDIA/open-gpu-kernel-modules) — open kernel modules (userspace blob remains closed) — snapshot [`files/github-docs/NVIDIA-open-gpu-kernel-modules-README.md`](files/github-docs/NVIDIA-open-gpu-kernel-modules-README.md)
- Official PTX (not SASS): [docs.nvidia.com PTX ISA](https://docs.nvidia.com/cuda/parallel-thread-execution/)

### Apple Silicon (GPU / AMX / ANE)

| Artifact | What | Local / URL |
|----------|------|-------------|
| [dougallj/applegpu](https://github.com/dougallj/applegpu) | M1 G13 GPU ISA: docs, disassembler, emulator, assembler. Docs: [dougallj.github.io/applegpu](https://dougallj.github.io/applegpu/docs.html) | [`files/github-docs/applegpu-README.md`](files/github-docs/applegpu-README.md) |
| [AsahiLinux/gpu](https://github.com/AsahiLinux/gpu) + [docs](https://github.com/AsahiLinux/docs) + [m1n1](https://github.com/AsahiLinux/m1n1) | AGX driver RE playground | [`files/github-docs/AsahiLinux-docs-README.md`](files/github-docs/AsahiLinux-docs-README.md) |
| Alyssa Rosenzweig series | [Dissecting the M1 GPU, part I](https://alyssarosenzweig.ca/blog/asahi-gpu-part-1.html) | — |
| [corsix/amx](https://github.com/corsix/amx) | **Apple AMX** (undocumented matrix coprocessor) instruction set | [`files/github-docs/corsix-amx-README.md`](files/github-docs/corsix-amx-README.md) |
| [eiln/ane](https://github.com/eiln/ane) | Reverse-engineered **Linux ANE driver** (Asahi) | [`files/github-docs/eiln-ane-README.md`](files/github-docs/eiln-ane-README.md) |
| [hollance/neural-engine](https://github.com/hollance/neural-engine) | ANE notes / undocumented Core ML paths | [`files/github-docs/hollance-neural-engine-README.md`](files/github-docs/hollance-neural-engine-README.md) |
| [hack-different/apple-knowledge](https://github.com/hack-different/apple-knowledge) | Machine-readable Apple hardware + RE notes | [`files/github-docs/apple-knowledge-README.md`](files/github-docs/apple-knowledge-README.md) |
| M4 ANE writeup | [Inside the M4 Apple Neural Engine](https://maderix.substack.com/p/inside-the-m4-apple-neural-engine) | — |

### CPU microarchitecture (measured / reconstructed)

| Artifact | What | Local / URL |
|----------|------|-------------|
| Agner Fog *Instruction tables* | x86/x64 latency/throughput/µops, many µarchs | [`files/reverse-eng/agner-fog-instruction-tables.pdf`](files/reverse-eng/agner-fog-instruction-tables.pdf) |
| Agner Fog *Microarchitecture* | Intel/AMD pipeline RE notes (278 pp) | [`files/reverse-eng/agner-fog-microarchitecture.pdf`](files/reverse-eng/agner-fog-microarchitecture.pdf) |
| [uops.info](https://uops.info/) | Automated x86 port/latency measurements | — |
| [InstLatx64](https://github.com/InstLatx64/InstLatx64) | CPUID / instlat dumps | — |
| [chipsandcheese.com](https://chipsandcheese.com/) | Modern Zen / Apple / GPU floorplan + perf writeups | — |
| [WikiChip](https://en.wikichip.org/) | Process / µarch encyclopedia | — |

### TPU / NPU

| Artifact | What | Local / URL |
|----------|------|-------------|
| Jouppi et al. *In-Datacenter Performance Analysis of a TPU* (arXiv:1704.04760) | **TPU v1** architecture (systolic array) — vendor paper, not RE, but the canonical TPU-v1 doc | [`files/reverse-eng/tpu-v1-in-datacenter-arxiv-1704.04760.pdf`](files/reverse-eng/tpu-v1-in-datacenter-arxiv-1704.04760.pdf) |
| TPU v4 (already in papers/) | [`files/papers/tpu-v4-isca23.pdf`](files/papers/tpu-v4-isca23.pdf) | — |
| [google-coral/coralnpu](https://github.com/google-coral/coralnpu) | **Open** RISC-V edge NPU (not RE; Google published the RTL) | [`files/github-docs/coralnpu-README.md`](files/github-docs/coralnpu-README.md) |
| Qualcomm Hexagon / HTP compiler RE | [datavorous writeup](https://datavorous.github.io/writing/qairt/) — VTCM, silent precision rewrites. No public Hexagon NPU ISA. | — |
| Qualcomm NPU kernel (security) | [GitHub Security Lab: Fall of the machines](https://github.blog/security/vulnerability-research/fall-of-the-machines-exploiting-the-qualcomm-npu-neural-processing-unit-kernel-driver/) | — |

AMD RDNA/CDNA and Intel Xe have **vendor ISA PDFs** (GPUOpen / Intel) — not listed here because they are official. Datacenter Gaudi / Trainium / Inferentia / Groq / Cerebras / MTIA / Maia ISAs remain unpublished; no high-quality public RE dumps found this pass.

## Chinese resources (still not mirrored)

Same three as the README — PDFs remain account- or conference-gated this pass:

- CAICT 智算中心液冷产业全景研究报告（2025）and 冷板式液冷报告（2024）
- Huawei AI DC / AIDC 机房参考设计白皮书
- T/CECS 1903-2025 智能计算中心设计标准
- Plus [DeepLink SuperPod 白皮书](https://github.com/DeepLink-org/superpod-whitepaper) (source, not a single PDF)

## Still gated / next harvest

- Hopper / Blackwell / Rubin **architecture whitepapers** on `resources.nvidia.com` (login wall). HTML product pages are public.
- NVIDIA 800 VDC full WP (`nvdam.nvidia.com` share link).
- Spectrum-X WP, SuperMicro SuperCluster+Spectrum-X PDF (403 this pass).
- H200 SuperPOD RA HTML path 404 at the obvious URL; use B200/GB200 RAs + H100 RA.
- Alibaba HPN and Meta RoCE training papers (ACM).
- Most Zaius `*-GBR-*.zip` via Git LFS (`git lfs pull` in that repo).
- Olympus 7z motherboard packs (16–20 MB) — left in upstream to avoid duplicating 50+ MB.

## Search log (this pass)

Queries covered: GitHub `NVLink`/`NVL72`/`SuperPOD`/`HGX`/`GB200`, `org:opencomputeproject` (OAI, OCDAI, Catalina, DC-SCM, Olympus, Zaius, Rack & Power), code search for OCP Gerbers, Firecrawl PDF/GitHub categories, NVIDIA docs SuperPOD `_downloads/*.pdf`, IEA Energy-and-AI, ASHRAE TC 9.9, OCP contributions DB, 800 VDC, Spectrum-X, UALink (spec still consortium-gated), Google Research Jupiter Evolving storage URL.

**RE follow-up (same day):** GitHub SASS/CuAssembler/maxas/turingas/envytools/applegpu/AMX/ANE/Asahi/open-gpu-doc; arXiv Jia Volta/Turing, Ampere 2208.11174, Hopper 2402.13499 + 2501.12084, Tensor Cores 2206.02874, TPU v1 1704.04760; Agner Fog manuals; Qualcomm Hexagon compiler writeups; Coral NPU RTL.
