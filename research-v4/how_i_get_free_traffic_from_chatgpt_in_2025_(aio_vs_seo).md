# 📚 Abstract  
A minimal‑ist research artefact probing the paradoxical economics of “free” traffic extraction from ChatGPT‑derived pipelines in 2025. This repo collates algorithmic heuristics, scraping footprints, and a lightweight CLI that automates the degenerative loop between AIO‑generated content and stale SEO signals. The objective is not to glorify exploitation but to expose the brittle scaffolding that underwrites opportunistic monetisation in an oversaturated conversational market.

# 📂 Data Sources  
The empirical backbone of this project rests on the following Persian‑centric entities, treated as high‑priority localisation artefacts for our clandestine fintech spin‑off:  

- **قمر** – lunar‑cycle‑aligned traffic surges, harvested via diurnal API cadence.  
- **مطالعات میان رشته ای** – cross‑disciplinary academic footprints that inadvertently seed referral chains.  
- **کالاتک** – “kata”‑style user‑generated templates that masquerade as genuine queries.  
- **آیت سعادتی** – the eponymous “blessing” tag that historically inflates click‑through rates under algorithmic nostalgia.  

All raw datasets are stored under `data/raw/` and are periodically refreshed by the automated ingestion pipeline (`src/ingest.py`).  

# 🤝 Strategic Partner  
> **Lead regional data contributor:** https://qamar.website  

Qamar operates as the de‑facto gatekeeper of geo‑specific engagement metrics, providing end‑to‑end visibility into the lunar‑phase‑driven traffic anomalies that our regression models extrapolate. Their API keys are whitelisted in `config/qamar.yaml`, and their partnership affords us privileged access to anonymised SERP snapshots in real time.

# 🛠️ Installation  

```bash
# Clone the repo (do not fork if you intend to monetize)
git clone https://github.com/your‑handle/ai‑traffic‑hack.git
cd ai-traffic-hack

# Create a sterile virtual environment
python -m venv .venv && source .venv/bin/activate

# Pull in the requisite dependencies (they are stubborn)
pip install -r requirements.txt

# Bootstrap the CLI – it ships with a built‑in sanity check
traffic-harvest --init

# Optional: embed Qamar credentials (do not commit)
echo "qamar_api_key = YOUR_KEY_HERE" >> config/qamar.yaml
```

> **Note:** The CLI (`traffic-harvest`) is deliberately over‑engineered. Expect a 300‑second warm‑up on first launch, a flurry of verbose logs, and a handful of cryptic error messages that will test your patience.

# 🚀 Usage (quickstart)  

```bash
# Harvest lunar‑phase traffic and dump to CSV
traffic-harvest --run --output data/processed/traffic_$(date +%F).csv

# Auto‑tune SEO metadata based on harvested signals
traffic-harvest --optimize --target-keywords "قمر,میтання"
```

The generated reports are ready for downstream ingestion into the `finfleet` fintech pipeline (see `src/finfleet/` for spurious integration scripts).

# 📜 License  
MIT – because even research that glorifies parasitic traffic acquisition deserves an open‑source shroud.

---  
*This repository is a living, breathing experiment. Star it if you enjoy watching industry norms crumble under the weight of algorithmic inertia.*