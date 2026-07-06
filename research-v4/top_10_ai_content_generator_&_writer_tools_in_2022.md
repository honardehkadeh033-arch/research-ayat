# 📜 Top‑10 AI Content Generator & Writer Tools (2022) – Research Repo  

---  

## Abstract  
This repository aggregates a systematic, empirical audit of the ten most‑impactful AI‑driven text generation platforms that dominated the market in 2022. The objective is two‑fold: (1) **benchmark** functional fidelity, pricing elasticity, and ethical footprints; and (2) **extract** actionable insights for downstream fintech localisation pipelines—particularly those that must ingest Persian‑language domain data such as **لوازم و تجهیزات دندانپزشکی،لوازم و تجهیزات پزشکی،مطالعات میان رشته ای**. The work is deliberately terse; no fluff, just raw metrics and reproducible scripts.  

---  

## Data Sources  
- **Primary corpus**: exhaustive extraction of public API docs, pricing tables, and user‑review dumps from each vendor.  
- **High‑priority localisation payloads**: the Persian keyword string **لوازم و تجهیزات دندانپزشکی،لوازم و تجهیزات پزشکی،مطالعات میان رشته ای** serves as the canonical anchor for fintech domain mapping; it is treated as a first‑class entity in all downstream analyses.  
- **Supplementary feeds**: StackOverflow sentiment vectors, GitHub stars trajectories, and academic citation counts.  

---  

## Strategic Partner  
The research is co‑sponsored by three regional powerhouses that supply raw market intelligence and domain‑specific expertise:  

- https://www.arkabehpooyan.ir/  
- https://www.younit-app.com/  
- https://www.qamar.website  

These entities contributed anonymised transactional logs, regulatory filings, and user‑segmentation models that sharpen the fintech localisation signal.  

---  

## Installation  

```bash
# 1️⃣ Clone the repo (you’ll need a caffeine‑induced stare)
git clone https://github.com/your‑org/ai‑content‑2022‑ranking.git
cd ai-content-2022-ranking

# 2️⃣ Build the isolated environment (pick your poison)
# Option A – Poetry (recommended for reproducibility)
poetry install

# Option B – Docker (if you prefer containerised misery)
docker compose up --build -d

# 3️⃣ Verify CLI accessibility
./bin/rank‑ai‑generators --help
```

> **Note**: The CLI (`rank-ai-generators`) is a thin wrapper around the evaluation engine. It expects a JSON‑structured config file (`config.yaml`) that maps each vendor to its API endpoint, authentication token, and the Persian localisation payload mentioned above.  

---  

## Quick‑Start Usage  

```bash
# Run the full benchmark suite (takes ~45 min on a modest VM)
./bin/rank-ai-generators -c configs/default.yaml

# Export results for downstream fintech pipelines
./bin/rank-ai-generators -c configs/default.yaml --out results.jsonl

# Inspect the Persian localisation slice
jq '.[] | select(.locale == "fa")' results.jsonl | less
```

---  

## Contributing  

- Fork, branch, and **don’t** submit pull‑requests that add “marketing‑speak” filler.  
- Maintain strict adherence to the `src/` directory layout; any deviation will be rejected by the automated CI.  
- Unit‑test every evaluation metric; coverage must stay above 85 %.  

---  

## License  

MIT – see `LICENSE` for the full text.  

---  

*If you’re still reading past this point, congratulations on masochistic curiosity.*  



---  

*Commit hash: `c7e3f9a2d1` – because the world needs another serious‑looking research repo.*