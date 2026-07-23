# Free High-Quality Books & Guides on AI Deployment, Data Centers, Rack Design & Optimal Layouts

Curated collection of free / open-access high-quality resources. Primary focus remains physical AI infrastructure (data centers, racks, liquid cooling, power, NVLink/Aquila, Chinese AIDC materials). Expanded software section for building AI from scratch.

## Core Full Books (Physical + Systems)
- The Data Center as a Computer 4th Ed (Barroso et al., Google) – https://datacenter-book.org/
- Energy Efficient Servers (Gough et al., Intel) – Springer OA
- Machine Learning Systems (mlsysbook.ai, Harvard)

## Energy / Layout / Rack / Interconnect
- LBNL/FEMP Best Practices Guide for Energy-Efficient Data Center Design (2024)
- Schneider WP 144: Establishing a Floor Plan
- OCP Open Rack V3 + Brazos / Mount Diablo liquid cooling
- NVIDIA GB200/GB300 NVL72 OCP contributions + reference architectures
- NVIDIA NVLink + 800 VDC blogs
- Google Aquila (NSDI’22) + Jupiter papers

## Chinese Free Resources
- CAICT 智算中心液冷产业全景研究报告（2025） + 冷板式液冷报告（2024）
- Huawei AI DC / AIDC 机房参考设计白皮书
- T/CECS 1903-2025 智能计算中心设计标准

## Building AI / LLMs from Scratch (Software)
High-quality free educational resources for implementing models, training pipelines, and systems from first principles:

- **Stanford CS336: Language Modeling from Scratch** (Spring 2026)  
  Full free YouTube lecture series + course materials + assignments. Taught by Percy Liang & Tatsunori Hashimoto. End-to-end: tokenization → architectures → training → scaling laws → inference → alignment. Course site: https://cs336.stanford.edu/ | Playlist available on Stanford Online YouTube. One of the strongest academic “from scratch” courses currently available.

- **Sebastian Raschka – Build a Large Language Model (From Scratch)**  
  Official free code repo: https://github.com/rasbt/LLMs-from-scratch (99k+ stars)  
  Step-by-step PyTorch GPT-style implementation (data, attention, pretraining, finetuning). Free companion videos.

- **Andrej Karpathy – Neural Networks: Zero to Hero**  
  https://karpathy.ai/zero-to-hero.html  
  micrograd → makemore → full GPT. Companion: nanoGPT, build-nanogpt.

- **Maxime Labonne – LLM Course**  
  https://github.com/mlabonne/llm-course (80k+ stars)  
  Free structured roadmaps (Fundamentals → LLM Scientist → LLM Engineer) + Colab notebooks for fine-tuning, merging, quantization, evaluation, agents. Extremely practical.

- **Train LLM From Scratch**  
  https://github.com/FareedKhan-dev/train-llm-from-scratch  
  Pure PyTorch + The Pile + full SFT/RLHF/PPO/DPO/GRPO pipeline. Single-GPU friendly.

- **The Annotated Transformer** (Harvard NLP)  
  Classic annotated “Attention is All You Need” implementation.

- **Neural Networks from Scratch** (Harrison Kinsley / Sentdex)  
  Pure Python/NumPy neural nets. nnfs.io + free videos.

These complement the physical infrastructure collection by covering how the models that run in those racks are actually built and trained.

Repo continuously updated. Chinese full translations in progress.

Last updated: July 2026
