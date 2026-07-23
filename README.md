# Free High-Quality Books & Guides on AI Deployment, Data Centers, Rack Design & Optimal Layouts

Curated collection of **free / open-access** high-quality resources. Focused on comprehensive books and substantial guides from reputable sources (Google, Intel, DOE/NREL/LBNL, Harvard, OCP, Schneider, NVIDIA, Chinese institutions, etc.). No low-quality or pirated material.

## Core Full Books (Open Access / Free PDF)

### 1. The Data Center as a Computer: Designing Warehouse-Scale Machines, 4th Edition
- **Authors**: Luiz André Barroso, Urs Hölzle, Parthasarathy Ranganathan (Google)
- **Why essential**: The definitive treatment of warehouse-scale computers (WSCs). Covers architecture, power, cooling, networking, software stack, costs, modular design, sustainability, and AI/ML workloads. Directly relevant to modern AI training/inference clusters.
- **Free access**: https://datacenter-book.org/ (Download free PDF)

### 2. Energy Efficient Servers: Blueprints for Data Center Optimization
- **Authors**: Corey Gough, Ian Steiner, Winston Saunders (Intel)
- **Free access**: Springer Open Access – https://link.springer.com/book/10.1007/978-1-4302-6638-9

### 3. Machine Learning Systems (MLSysBook.ai)
- **Author/Editor**: Vijay Janapa Reddi (Harvard) + community
- **Free access**: https://mlsysbook.ai/

## High-Quality Free Guides

### Best Practices Guide for Energy-Efficient Data Center Design (2024)
- FEMP / NREL / LBNL – Free PDF: https://www.energy.gov/sites/default/files/2024-07/best-practice-guide-data-center-design_0.pdf

### Data Center Projects: Establishing a Floor Plan (Schneider WP 144)
- Optimal rack/room layout principles.

## Rack Design & Open Hardware (OCP + NVL72)

- **OCP Open Rack V3** + liquid cooling / blind-mate / power sidecar (Mount Diablo, Brazos) specs: https://www.opencompute.org/
- **NVIDIA GB200 / GB300 NVL72** rack and tray designs contributed to OCP (liquid-cooled, 72-GPU NVLink domain). See NVIDIA Technical Blog and OCP documentation for the contributed CAD/specs.
- NVIDIA official NVL72 reference architectures, network logical architecture, and deployment guides on docs.nvidia.com (free).

## Interconnects, Power & Cooling White Papers

### NVIDIA
- NVLink scale-up network details (5th/6th gen, NVL72):
  https://developer.nvidia.com/blog/nvidia-nvlink-the-scale-up-network-for-ai-factories/
- 800 VDC architecture for MW-scale AI racks:
  https://developer.nvidia.com/blog/nvidia-800-v-hvdc-architecture-will-power-the-next-generation-of-ai-factories/

### Google
- Aquila (NSDI ’22): https://www.usenix.org/system/files/nsdi22-paper-gibson.pdf
- Jupiter Rising (SIGCOMM ’15) and Jupiter Evolving (SIGCOMM ’22) – free via Google Research / ACM
- Brazos open-source liquid-to-air cooling sidecar for ORv3

## Chinese / Chinese-Institution Free Resources (English or downloadable)

- **CAICT** – Research Report on the Panorama of Liquid Cooling Industry in Intelligent Computing Center (August 2025). English version available. Free download from CAICT site: https://www.caict.ac.cn/english/research/whitepapers/ (look for the liquid cooling intelligent computing center report)
- Huawei AI Data Center / AIDC strategy materials and white papers (Chinese versions freely downloadable from Huawei enterprise site; cover liquid cooling, power POD, high-density designs).
- Chinese Engineering Science papers on high-density computing centers and safety (open access PDFs available via engineering.org.cn).
- Domestic standards such as T/CECS 1903-2025 Intelligent Computing Center Design Standard (public standard documents).

These cover Chinese approaches to liquid cooling, high-density racks (including Ascend-based supernodes), and intelligent computing center design under domestic constraints.

## Additional Strong Free Resources

- LBNL Center of Expertise toolkits: https://datacenters.lbl.gov/
- NVIDIA DGX / NVL72 / Spectrum-X architecture and deployment docs
- Ongoing OCP AI rack and liquid cooling contributions

## Notes

Full free textbooks remain rare. The above are the highest-quality publicly available technical resources from the actual builders (Google, NVIDIA, OCP community, Chinese national labs/academies, DOE). Chinese materials are included where free English versions or downloadable PDFs exist.

Repo continuously updated. Contributions of additional verified free high-quality sources welcome.

Last updated: July 2026
