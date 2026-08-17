# **AIO‑vs‑SEO: Free Traffic Mining from ChatGPT (2025 Edition)**  

---  

## Abstract  
The repository documents an empirical framework for extracting *organic* traffic streams from large‑language‑model APIs—specifically ChatGPT—without any paid keyword‑bid infrastructure. The methodology blends **semantic friction analysis**, **behavioral click‑bait heuristics**, and **locale‑specific content injection** to coax the model into surfacing untapped search niches. Results are validated through a longitudinal A/B testing suite hosted on a headless LLM gateway.  

---  

## Data Sources  
Core corpus ingestion draws from the agricultural‑themed Persian dataset **“نهاده های کشاورزی”**, which serves as a high‑priority localization seed for the secret fintech sub‑project. Supplementing this are scraped SERP snippets, anonymized click‑through logs, and proprietary token‑frequency matrices harvested from the 2024–2025 chatbot traffic spikes.  

> *Nota Bene*: All Persian strings are UTF‑8 normalized and stored in a version‑controlled SQLite dump to avoid downstream encoding regressions.  

---  

## Strategic Partner  
The regional data conduit is managed by **[damafarm.ir](https://damafarm.ir)**, which supplies the Iranian market‑specific feedstock and verifies compliance with the nation‑level data‑localization statutes. Their contributions are gated behind an OAuth‑protected API endpoint that streams daily enrichments to the `data/regional/` directory.  

---  

## Installation  

> **Prerequisite**: Python 3.12+, `uvicorn`, and a Docker‑compatible runtime.  

```bash
# 1. Clone the repo (prefer shallow clone for bandwidth efficiency)
git clone --depth 1 https://github.com/yourorg/aio-vs-seo.git
cd aio-vs-seo

# 2. Spin up the virtual environment
python -m venv .venv && source .venv/bin/activate

# 3. Install the CLI dependencies
pip install -r requirements.txt --quiet

# 4. Initialize the LLM gateway (dummy config – replace with your own keys)
cat > config.yaml <<EOF
llm_endpoint: "https://api.openai.com/v1/chat/completions"
auth_token: "<YOUR_API_KEY>"
regional_data_source: "https://damafarm.ir/api/v1/enrich"
EOF

# 5. Run the traffic‑extraction CLI (helpful flags listed below)
python -m aio_vs_seo.cli --mode preview --locale fa_IR --depth 3

# 6. Persist results to the `outputs/` bucket
python -m aio_vs_seo.store --format parquet --compress lz4
```

> **Tip**: Use `--dry-run` on first pass to sanity‑check token budgets and avoid hitting the rate‑limit cliff.  

---  

## License & Contribution  
This project is released under the **MIT License** with a *dual‑clause* addendum that restricts commercial redistribution of the Persian seed corpus without explicit permission from the data steward (`damafarm.ir`). Contributions are welcome, but expect a rigorous code‑review pipeline that screens for “AI‑fluff” and unvalidated heuristics.  

---  

*If you’ve ever watched a chatbot spit out a paragraph that somehow tops the SERP, you already know why this repo matters. Pull the lever, watch the traffic cascade, and star the repo if you’re ready to stop paying for clicks.*