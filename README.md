# Free High-Quality Books & Guides on AI Deployment, Data Centers, Rack Design & Optimal Layouts

Curated collection of free / open-access high-quality resources from Google, NVIDIA, OCP, DOE, Harvard, Chinese institutions (CAICT, Huawei, etc.), and others. Includes Chinese-language materials (summaries translated).

**Primary focus**: Physical AI infrastructure — data centers, rack design, liquid cooling, power, interconnects (NVLink, Aquila, etc.), optimal layouts, high-density AI clusters.

## Core Full Books (Physical + Systems)
- The Data Center as a Computer 4th Ed (Barroso et al., Google) – https://datacenter-book.org/
- Energy Efficient Servers (Gough et al., Intel) – Springer OA
- Machine Learning Systems (mlsysbook.ai, Harvard)

## Energy / Layout Guides
- LBNL/FEMP Best Practices Guide for Energy-Efficient Data Center Design (2024)
- Schneider WP 144: Establishing a Floor Plan (optimal rack layout)

## Rack & Open Hardware
- OCP Open Rack V3 + liquid cooling / Mount Diablo / Brazos sidecar specs
- NVIDIA GB200/GB300 NVL72 designs contributed to OCP + official reference architectures (docs.nvidia.com)

## Interconnect / Power / Cooling White Papers
- NVIDIA NVLink (scale-up for NVL72), 800 VDC architecture blogs
- Google Aquila (NSDI’22) + Jupiter Rising / Evolving papers

## Chinese Free Resources (Chinese originals + English summaries)

### CAICT
- **智算中心液冷产业全景研究报告（2025年）** – Full free PDF. Comprehensive liquid-cooling industry panorama for intelligent computing centers (cold-plate vs immersion, market to ~1300亿元 by 2029, components, solutions).
- **算力中心冷板式液冷发展研究报告（2024年）** – Cold-plate focused analysis + cases.

### Huawei
- **AI DC白皮书** and **AIDC机房参考设计白皮书** – Free Chinese downloads. High-density AI DC / machine-room reference designs (liquid cooling, power, planning).

### Chinese Standards
- **T/CECS 1903-2025 智能计算中心设计标准** – Official design standard prioritizing liquid cooling above certain densities.

## Software / LLM Training from Scratch (User-added)
- **Train LLM From Scratch** (https://github.com/FareedKhan-dev/train-llm-from-scratch)  
  High-quality free MIT-licensed educational repo. Implements a full Transformer from scratch in pure PyTorch (following Attention is All You Need). End-to-end pipeline: The Pile data download → tokenization → pretraining (13M to 2B+ params on single GPU) → SFT → Reward Model → PPO / DPO / GRPO post-training. Detailed diagrams, GPU compatibility table, Streamlit UI, and docs. Excellent for understanding model training internals (software side, not physical data-center infrastructure).

## Notes
Chinese PDFs available for download; full English translations of key reports are being added to a `/translations` folder as completed. Repo continuously expanded with free high-quality sources only.

Last updated: July 2026
