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
  Full free YouTube lecture series + course materials + assignments. Percy Liang & Tatsunori Hashimoto. End-to-end: tokenization → architectures → training → scaling → inference → alignment. https://cs336.stanford.edu/

- **Sebastian Raschka – Build a Large Language Model (From Scratch)**  
  https://github.com/rasbt/LLMs-from-scratch (99k+ stars) + free companion videos. Gold-standard pure PyTorch GPT implementation.

- **Andrej Karpathy – Neural Networks: Zero to Hero**  
  https://karpathy.ai/zero-to-hero.html + nanoGPT / build-nanogpt.

- **Maxime Labonne – LLM Course**  
  https://github.com/mlabonne/llm-course (80k+ stars). Practical roadmaps + Colab notebooks (fine-tune, merge, quantize, agents).

- **Modern LLM Notebook**  
  https://github.com/walkinglabs/modern-llm-notebook  
  26 runnable Jupyter notebooks covering tokenizers, attention, MoE, LoRA, RLHF, KV cache, distillation, evaluation, etc. Strong modern-systems coverage.

- **datawhalechina/diy-llm**  
  Systematic Chinese course covering pretraining data engineering, tokenizer, Transformer, MoE, CUDA/Triton, distributed training, scaling laws, inference optimization, SFT/RLHF/GRPO. Progressive assignments.

- **Train LLM From Scratch**  
  https://github.com/FareedKhan-dev/train-llm-from-scratch  
  Pure PyTorch + The Pile + full post-training pipeline. Single-GPU friendly.

- **rasbt/LLM-workshop-2024**  
  Hands-on PyTorch workshop: tokenizer → GPT assembly → pretrain → load weights → instruction finetuning with LitGPT.

- **The Annotated Transformer** (Harvard NLP) + **Neural Networks from Scratch** (nnfs.io)

These complement the physical infrastructure collection by covering how the models that run in those racks are actually built and trained.

Repo continuously updated. Chinese full translations in progress.

Last updated: July 2026
