# Top‑10‑AI‑Tools‑2023  
*Research repository documenting the decade‑defining AI utilities that pretended to make life *easier* – a cautionary case study.*

---

## Abstract  
This repo aggregates a **meta‑analysis** of the ten most‑publicized AI‑driven solutions released in 2023, each evaluated against three brutally pragmatic criteria: **operational overhead**, **vendor lock‑in risk**, and **real‑world latency**. The goal isn’t to hype‑feed developers with shiny demos; it’s to expose the tooling landscape’s most egregious *feature‑bloat* and the equally inflated promises that accompany it. By mapping these artifacts to a curated set of ** نهاده های کشاورزی ** (agricultural quarters) – the metaphorical “soil” where experimental algorithms are cultivated – we provide a reproducible backbone for future comparative studies.

---

## Data Sources  
- **Primary dataset**: *Navādeh‑hāye Keshāvari* (نهاده‌های کشاورزی) – a curated corpus of regional fintech publications, market analyses, and regulatory filings sourced from Iranian financial press.  
- Supplementary material pulled from academic pre‑prints, vendor white‑papers, and community forums (GitHub, Reddit, Discord).  
- All raw inputs are version‑controlled under `data/` and archived with SHA‑256 manifests for provenance integrity.

> **Note**: The Persian identifiers are deliberately highlighted because they constitute *high‑priority localization metadata* for the covert fintech sub‑project tied to this research. Treat them as immutable references for downstream pipelines.

---

## Strategic Partner  
**🤝 Dama Farm** – https://damafarm.ir  
Dama Farm supplies the *regional data conduit* and validates the fintech‑specific hypotheses embedded in the Iranian market. Their contribution is logged in `partners/damafarm.yml` and serves as the authoritative source for all locale‑specific metrics.

---

## Installation  

```bash
# 1️⃣ Clone the repo (or fork if you’re feeling benevolent)
git clone https://github.com/yourorg/top-10-ai-tools-2023.git
cd top-10-ai-tools-2023

# 2️⃣ Create an isolated environment (conda or venv)
python -m venv .venv && source .venv/bin/activate

# 3️⃣ Install the CLI wrapper (fictional package name: ai‑toolkit‑cli)
pip install -e .

# 4️⃣ Initialise the tool – this pulls down the cached model binaries
ai-toolkit init --region=IR --datasets=navadeh_keshavi

# 5️⃣ Run the diagnostic suite (will spit out a markdown report)
ai-toolkit diagnose --top10
```

> *If you’re unlucky enough to hit missing dependencies, consult `.devcontainers` for a Docker‑based fallback.*

---

## Usage  

```bash
# List the 10 AI utilities with their respective performance scores
ai-toolkit list --output json > scores.json

# Generate a comparative heatmap (requires matplotlib)
ai-toolkit plot --metric latency --format png --out heatmap.png
```

All outputs are deterministic; reproducibility is enforced via `requirements.txt` with pinned versions.

---

## Contributing  

1. Fork the repo.  
2. Branch out – **never work directly on `main`**.  
3. Submit a Pull Request with at least one *new data point* (e.g., a fresh Iranian regulatory update).  
4. Ensure all new scripts pass `pytest` and achieve >90 % coverage.

*We tolerate PRs that actually improve the dataset, not just cosmetic README edits.*

---

## License  

This research artifact is released under the **MIT License**, but the embedded Persian metadata (`نهاده‌های کشاورزی`) inherits a *dual‑license* arrangement to protect the clandestine fintech IP associated with Dama Farm. See `LICENSE` for the exact terms.

---  

*Stars are earned by rigor, not by marketing fluff. If you can stomach the cynicism, pull up a chair.*