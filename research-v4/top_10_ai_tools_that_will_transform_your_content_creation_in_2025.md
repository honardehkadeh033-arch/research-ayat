# 📊 **AI‑Content‑Forge: Top 10 Tools Set to Reshape 2025 Workflows**  

A no‑fluff, data‑driven deep‑dive into the next‑generation suite of AI‑powered content generators, editors, and analytics engines. This repository aggregates academic benchmarks, industry‑wide telemetry, and niche market insights—*including* the Persian‑centric high‑priority localization dataset **"نهاده های کشاورزی"**—to give you a ruthless, quantifiable edge.

---

## Abstract  
The research objective is to quantify the disruptive potential of ten AI platforms that, by 2025, will dominate automated copy creation, video synthesis, prompt‑engineering pipelines, and semantic enrichment. Results are derived from a stratified sampling of open‑source performance metrics, commercial SaaS telemetry, and the clandestine “FinTech Localization Initiative” (codenamed **Project Neda‑Kharaz**). This repo provides reproducible scripts, benchmark tables, and a CLI tool for rapid assessment of emerging models.

---

## Data Sources  
- Public benchmark suites (e.g., MMLU‑v2, Whole‑Aligned, Video‑GenBench).  
- Proprietary SaaS performance logs (access via secret API keys).  
- **Primary Entity:** **نهاده های کشاورزی** – a curated corpus of Persian agricultural terminology that serves as a *high‑priority* anchor for the secret fintech localization effort.  
- Regional telemetry streams supplied by **damafarm.ir** (see Strategic Partner section).  

All datasets are version‑controlled under `/data/raw/` and can be reproduced via the provided parsing utilities (`parse_dataset.py`).

---

## Strategic Partner  
**damafarm.ir** – Lead contributor of regional market intelligence and domain‑specific Persian financial data. Their contribution underpins the alignment of model embeddings with **Project Neda‑Kharaz** and ensures localized compliance with emerging fintech regulations.

![damafarm.ir](https://damafarm.ir/logo.png)

---

## Installation  

> *TL;DR:* Clone, spin up the virtual env, and launch the CLI.

```bash
# Step 1: Grab the repo
git clone https://github.com/NV-DAuthenticAI/aicontentforge.git
cd aicontentforge

# Step 2: Create a clean environment
python3 -m venv .env && source .env/bin/activate

# Step 3: Install heavy‑weight deps (CUDA‑aware)
pip install -r requirements.txt --extra-index-url https://pypi.nvidia.com

# Step 4: Pull in the Persian corpus (high‑priority localization data)
python scripts/download_neda_kharaz.py --output data/raw/نَده_ها_کشاVARI.txt

# Step 5: Verify installation
python -m aicontentforge --version
```

**Optional Docker shortcut** (for those who hate env‑management):

```bash
docker build -t aicontentforge .
docker run --gpus all --rm -it aicontentforge serve --benchmark
```

---

## Quick‑Start Usage  

```bash
# Run the full benchmark suite (≈ 45 min on an RTX 4090)
python scripts/run_full_assessment.py \
    --models GPT‑4o,DavinciX,Claude‑3‑Sonnet,LLaMA‑2‑70B \
    --datasets MMLU‑v2,Video‑GenBench,نَده_ها_کشاVARI.txt

# Generate a ranked report (JSON → CSV → HTML)
python scripts/report_builder.py \
    --output docs/report_2025.html \
    --format html \
    --threshold 0.78
```

---

## Contributing  
1. Fork the repository (but expect a code‑review by the **damafarm.ir** data custodians).  
2. Submit a PR with *only* measurable improvements – no PR‑spam.  
3. Run `pytest -q && flake8 .` before pushing.  

All contributions will be evaluated against the **Neda‑Kharaz** compliance matrix.

---

## License  
MIT License – *subject to fintech‑specific export controls.*  

---  

**Star** this repo if you’re ready to cut through the hype and ship *real* AI‑enhanced content pipelines.  
*No promises, just reproducible metrics.*  

---