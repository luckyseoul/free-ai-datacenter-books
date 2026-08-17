# Free High-Quality Books & Guides on AI Deployment, Data Centers, Rack Design & Optimal Layouts

Curated **offline** collection. Document binaries and README snapshots live under [`files/`](files/). External URLs have been replaced with local paths where a free download was available.

## Core Full Books (Physical + Systems)

| Title | Local file |
|-------|------------|
| **The Data Center as a Computer 4th ed.** (Barroso/Hölzle/Ranganathan, 362 pp, full PDF) | [`files/core/The-Data-Center-as-a-Computer-4th.pdf`](files/core/The-Data-Center-as-a-Computer-4th.pdf) |
| Same — chapter Markdown mirror | [`files/core/datacenter-as-a-computer-4th-md/`](files/core/datacenter-as-a-computer-4th-md/) |
| Same — CN translation Markdown | [`files/core/datacenter-as-a-computer-cn-md/`](files/core/datacenter-as-a-computer-cn-md/) |
| 3rd ed. sample (Google pub 45406) | [`files/core/The-Data-Center-as-a-Computer-3rd.pdf`](files/core/The-Data-Center-as-a-Computer-3rd.pdf) |
| Energy Efficient Servers (Gough et al., Intel / Springer OA) | [`files/core/Energy-Efficient-Servers.pdf`](files/core/Energy-Efficient-Servers.pdf) |
| Machine Learning Systems Vol. 1 (mlsysbook.ai) | [`files/core/Machine-Learning-Systems-Vol1.pdf`](files/core/Machine-Learning-Systems-Vol1.pdf) |
| Machine Learning Systems Vol. 2 | [`files/core/Machine-Learning-Systems-Vol2.pdf`](files/core/Machine-Learning-Systems-Vol2.pdf) |
| StaffML paper (companion) | [`files/core/StaffML-Paper.pdf`](files/core/StaffML-Paper.pdf) |

> **Note:** Full 4th ed PDF obtained via Springer OA content path (datacenter-book.org API is bot-gated). Workarounds catalog: [`files/core/SOURCES.md`](files/core/SOURCES.md).

Full 2026-08-17 harvest (NVLink gens 1–6, SuperPOD RAs, OCP Gerbers, GitHub, IEA/ASHRAE): **[`CATALOG.md`](CATALOG.md)**.

## Energy / Layout / Rack / Interconnect

| Resource | Local file |
|----------|------------|
| FEMP Best Practices Guide for Energy-Efficient Data Center Design (2024) | [`files/energy-cooling/FEMP-Best-Practices-Data-Center-Design-2024.pdf`](files/energy-cooling/FEMP-Best-Practices-Data-Center-Design-2024.pdf) |
| LBNL/FEMP Best Practices (historical Wayback copy) | [`files/energy-cooling/LBNL-FEMP-Best-Practices.pdf`](files/energy-cooling/LBNL-FEMP-Best-Practices.pdf) |
| IEA *Energy and AI* (2025) | [`files/energy-cooling/IEA-Energy-and-AI-2025.pdf`](files/energy-cooling/IEA-Energy-and-AI-2025.pdf) |
| IEA *Key Questions on Energy and AI* (2026) | [`files/energy-cooling/IEA-Key-Questions-on-Energy-and-AI-2026.pdf`](files/energy-cooling/IEA-Key-Questions-on-Energy-and-AI-2026.pdf) |
| ASHRAE TC 9.9 power-equipment thermal guidelines | [`files/energy-cooling/ASHRAE-TC99-Power-Equipment-Thermal-Guidelines.pdf`](files/energy-cooling/ASHRAE-TC99-Power-Equipment-Thermal-Guidelines.pdf) |
| ASHRAE TC 9.9 storage thermal guidelines | [`files/energy-cooling/ASHRAE-TC99-Storage-Thermal-Guidelines.pdf`](files/energy-cooling/ASHRAE-TC99-Storage-Thermal-Guidelines.pdf) |
| EPC 800 VDC → 12.5 V (NVIDIA 800 VDC ecosystem) | [`files/energy-cooling/EPC-800VDC-to-12.5V.pdf`](files/energy-cooling/EPC-800VDC-to-12.5V.pdf) |
| Google Aquila (NSDI’22, Gibson et al.) | [`files/papers/aquila-nsdi22.pdf`](files/papers/aquila-nsdi22.pdf) |
| Google Jupiter Rising | [`files/papers/google-jupiter-rising.pdf`](files/papers/google-jupiter-rising.pdf) |
| Google Jupiter Evolving (SIGCOMM’22, OCS) | [`files/papers/jupiter-evolving-sigcomm22.pdf`](files/papers/jupiter-evolving-sigcomm22.pdf) |
| ByteDance MegaScale (NSDI’24) | [`files/papers/megascale-nsdi24.pdf`](files/papers/megascale-nsdi24.pdf) |
| Rail-only (arXiv:2307.12169) | [`files/papers/rail-only-arxiv-2307.12169.pdf`](files/papers/rail-only-arxiv-2307.12169.pdf) |
| TPU v4 (ISCA’23) | [`files/papers/tpu-v4-isca23.pdf`](files/papers/tpu-v4-isca23.pdf) |

Harvest methods for blocked hosts: see [`files/core/SOURCES.md`](files/core/SOURCES.md).

## NVLink / NVSwitch / SuperPOD (architecture)

| Resource | Local file |
|----------|------------|
| Pascal (NVLink 1) architecture WP | [`files/nvlink/pascal-architecture-whitepaper.pdf`](files/nvlink/pascal-architecture-whitepaper.pdf) |
| Volta (NVLink 2 + first NVSwitch) architecture WP | [`files/nvlink/volta-architecture-whitepaper.pdf`](files/nvlink/volta-architecture-whitepaper.pdf) |
| Ampere A100 (NVLink 3) architecture WP | [`files/nvlink/ampere-architecture-whitepaper.pdf`](files/nvlink/ampere-architecture-whitepaper.pdf) |
| Turing architecture WP | [`files/nvlink/turing-architecture-whitepaper.pdf`](files/nvlink/turing-architecture-whitepaper.pdf) |
| Li et al. GPU interconnect eval (NVLink 1/2 vs PCIe) | [`files/papers/gpu-interconnect-eval-arxiv-1903.04611.pdf`](files/papers/gpu-interconnect-eval-arxiv-1903.04611.pdf) |
| DGX SuperPOD RA — H100 | [`files/superpod-ra/RA-DGX-H100-SuperPOD.pdf`](files/superpod-ra/RA-DGX-H100-SuperPOD.pdf) |
| DGX SuperPOD RA — B200 | [`files/superpod-ra/RA-DGX-B200-SuperPOD.pdf`](files/superpod-ra/RA-DGX-B200-SuperPOD.pdf) |
| DGX SuperPOD RA — GB200 NVL72 | [`files/superpod-ra/RA-DGX-GB200-SuperPOD.pdf`](files/superpod-ra/RA-DGX-GB200-SuperPOD.pdf) |

Generation table (NVLink 1 → 6 / NVL72 / NVLink-C2C) is in [`CATALOG.md`](CATALOG.md). Hopper/Blackwell/Rubin WPs remain on `resources.nvidia.com` (gated).

## Gerbers / OCP board files

NVIDIA does not publish NVLink switch or GPU Gerbers. Closest open packs:

| Pack | Local file |
|------|------------|
| Meta Catalina **DC-SCM** PCB artwork (`.art` / `.drl` Gerbers) | [`files/cad-gerber/Catalina-DC-SCM-artwork-OCP.zip`](files/cad-gerber/Catalina-DC-SCM-artwork-OCP.zip) |
| OpenPOWER Barreleye G2 **SXM2 riser** CAM/Gerber job | [`files/cad-gerber/Barreleye-G2-SXM2-RISER-EVT-HW-GBR.tgz`](files/cad-gerber/Barreleye-G2-SXM2-RISER-EVT-HW-GBR.tgz) |

More OCP CAD (Catalina tray, Olympus 7z, Zaius LFS Gerbers): [`files/cad-gerber/README.md`](files/cad-gerber/README.md) and [`CATALOG.md`](CATALOG.md).

## Chinese Free Resources

- CAICT 智算中心液冷产业全景研究报告（2025） + 冷板式液冷报告（2024）
- Huawei AI DC / AIDC 机房参考设计白皮书
- T/CECS 1903-2025 智能计算中心设计标准

(Place PDFs under `files/chinese/` when obtained.)

## Building AI / LLMs from Scratch (Educational)

| Resource | Local snapshot |
|----------|----------------|
| Stanford CS336 course page | [`files/courses/cs336-stanford.html`](files/courses/cs336-stanford.html) |
| Sebastian Raschka – Build a Large Language Model (From Scratch) | [`files/software-docs/LLMs-from-scratch-README.md`](files/software-docs/LLMs-from-scratch-README.md) |
| Andrej Karpathy – Neural Networks: Zero to Hero | [`files/courses/karpathy-zero-to-hero.html`](files/courses/karpathy-zero-to-hero.html) |
| Maxime Labonne – LLM Course | [`files/software-docs/llm-course-README.md`](files/software-docs/llm-course-README.md) |
| Modern LLM Notebook | [`files/software-docs/modern-llm-notebook-README.md`](files/software-docs/modern-llm-notebook-README.md) |
| Train LLM From Scratch | [`files/software-docs/train-llm-from-scratch-README.md`](files/software-docs/train-llm-from-scratch-README.md) |

## Foundational Free AI / ML Textbooks

| Title | Local file |
|-------|------------|
| Understanding Machine Learning: From Theory to Algorithms (Shalev-Shwartz & Ben-David) | [`files/ml-textbooks/understanding-machine-learning-theory-algorithms.pdf`](files/ml-textbooks/understanding-machine-learning-theory-algorithms.pdf) |
| Mathematics for Machine Learning (Deisenroth, Faisal, Ong) | [`files/ml-textbooks/mml-book.pdf`](files/ml-textbooks/mml-book.pdf) |

## Practical AI Tooling & Local Inference (README snapshots)

Living software projects are represented by offline README snapshots (not full git history):

- [`files/software-docs/llama.cpp-README.md`](files/software-docs/llama.cpp-README.md)
- [`files/software-docs/vllm-README.md`](files/software-docs/vllm-README.md)
- [`files/software-docs/ollama-README.md`](files/software-docs/ollama-README.md)
- [`files/software-docs/LocalAI-README.md`](files/software-docs/LocalAI-README.md)
- [`files/software-docs/transformers-README.md`](files/software-docs/transformers-README.md)
- [`files/software-docs/OpenHands-README.md`](files/software-docs/OpenHands-README.md)

## Data Ingestion / Web-to-LLM Tools (README snapshots)

- [`files/software-docs/firecrawl-README.md`](files/software-docs/firecrawl-README.md)
- [`files/software-docs/crawl4ai-README.md`](files/software-docs/crawl4ai-README.md)
- [`files/software-docs/browser-use-README.md`](files/software-docs/browser-use-README.md)
- [`files/software-docs/markitdown-README.md`](files/software-docs/markitdown-README.md)

## Free Certification Study Resources

AWS / CISSP shared Drive folders are not mirrored (account-gated). Add local study packs under `files/certs/` if desired.

## GitHub catalogs (README snapshots, 2026-08-17)

OCP AI fabrics, NVLink tooling, and awesome-lists live under [`files/github-docs/`](files/github-docs/). Highlights: `OCP-OCDAI-training-fabric`, `OCP-OAI`, Catalina/Olympus/Zaius, `NVIDIA/topograph`, `NVIDIA/Fabric-Manager-Client`, `awesome-gpu-engineering`, `awesome-ai-accelerators`, `awesome-hpc`, SemiAnalysis InferenceX.

## Layout

```
files/
  core/           # full books
  ml-textbooks/   # foundational textbooks
  courses/        # course page HTML snapshots
  software-docs/  # project README snapshots
  energy-cooling/ # FEMP / IEA / ASHRAE / 800 VDC
  nvlink/         # NVLink-era GPU architecture whitepapers
  superpod-ra/    # NVIDIA DGX SuperPOD reference architectures
  papers/         # conference / arXiv PDFs
  cad-gerber/     # OCP Gerbers (DC-SCM, SXM2 riser)
  github-docs/    # GitHub README snapshots
```

Last updated: 2026-08-17 — SuperPOD RAs, NVLink WPs, IEA/ASHRAE, OCP Gerbers, GitHub catalogs. See [`CATALOG.md`](CATALOG.md).
