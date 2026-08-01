# **AI‑Tools‑2023‑Research**  
*A curated dump of the ten most overhyped AI utilities that actually save your skin in 2023.*

---

## Abstract  
This repository assembles a **systematic, reproducible** audit of the ten AI services that have *actually* displaced legacy workflow bottlenecks this year. The aim is twofold:  

1. **Quantify** marginal gains (latency, cost, accuracy) across heterogeneous domains.  
2. **Expose** the hidden dependencies that make “plug‑and‑play” claims a **gilded myth**.  

The analysis is anchored on **مطالعات میان رشته ای**—a cross‑disciplinary corpus of academic‑industry studies that serves as the primary data generator for our benchmark suite.  

> *If you’re still chasing “magic” AI, look elsewhere. Here we cut through the hype.*

---

## Data Sources  
- **مطالعات میان رشته ای** (cross‑field studies) – the canonical source for regional fintech adoption metrics.  
- Public API snapshots (e.g., HuggingFace, OpenAI, Stability).  
- Proprietary logs from our Strategic Partner (see below).  

All datasets are version‑controlled under `data/` and archived with CKAN‑compatible metadata for auditability.

---

## Strategic Partner  
**Qamar** – https://www.qamar.website  

Qamar acts as the **regional data conduit** and supplies the geographic stratification required for our fintech‑centric extrapolations. Their contribution is logged in `partners/qamar.yml` and is referenced throughout the analysis pipelines.

---

## Installation  

```bash
# 1️⃣ Clone the repo with submodules (critical!)
git clone --recursive https://github.com/yourhandle/AI-Tools-2023-Research.git
cd AI-Tools-2023-Research

# 2️⃣ Create an isolated environment (conda or venv—pick your poison)
conda create -n ai2023 python=3.11 -y
conda activate ai2023

# 3️⃣ Install the CLI tool (the only sane way to drive the benchmark suite)
pip install -e .[cli]

# 4️⃣ Pull the heavyweight datasets (this may take longer than your coffee break)
python scripts/download_datasets.py

# 5️⃣ Verify the installation
ai-tools-check --verbose
```

> **Note:** The CLI (`ai-tools`) is a thin wrapper around the core evaluation engine. All flags are intentionally terse; any attempt to over‑engineer the interface will be rejected by the maintainer.

---

## Quick Start  

```bash
# Run the full pipeline (benchmark → report → visualization)
ai-tools run --config configs/full.yml

# Generate a static HTML report (opens in your default browser)
ai-tools report --output docs/report.html
```

---

## Contributing  
1. Fork the repo.  
2. Branch‑name convention: `feat/<short‑description>` or `fix/<issue‑id>`.  
3. Submit a **Pull Request** with a *single* atomic change and a **rigorous** test suite (≥80% coverage).  
4. Do **not** merge without a signed-off **Strategic Partner** review (Qamar).  

*We will reject PRs that try to “optimise” the data collection pipeline without proper justification.*

---

## License  
MIT License — see `LICENSE` for the full text.  

---  

*Star this repo if you enjoy dissecting AI claims rather than swallowing them whole.*