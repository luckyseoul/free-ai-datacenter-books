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

## Energy / Layout / Rack / Interconnect

| Resource | Local file |
|----------|------------|
| FEMP Best Practices Guide for Energy-Efficient Data Center Design (2024) | [`files/energy-cooling/FEMP-Best-Practices-Data-Center-Design-2024.pdf`](files/energy-cooling/FEMP-Best-Practices-Data-Center-Design-2024.pdf) |
| LBNL/FEMP Best Practices (historical Wayback copy) | [`files/energy-cooling/LBNL-FEMP-Best-Practices.pdf`](files/energy-cooling/LBNL-FEMP-Best-Practices.pdf) |
| Google Aquila (NSDI’22, Gibson et al.) | [`files/papers/aquila-nsdi22.pdf`](files/papers/aquila-nsdi22.pdf) |
| Google Jupiter Rising | [`files/papers/google-jupiter-rising.pdf`](files/papers/google-jupiter-rising.pdf) |

Harvest methods for blocked hosts: see [`files/core/SOURCES.md`](files/core/SOURCES.md).

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

## Layout

```
files/
  core/           # full books
  ml-textbooks/   # foundational textbooks
  courses/        # course page HTML snapshots
  software-docs/  # project README snapshots
  energy-cooling/ # (optional) FEMP / OCP / interconnect PDFs
```

Last updated: 2026-07-24 — offline document harvest; URLs replaced with local `files/` paths.
