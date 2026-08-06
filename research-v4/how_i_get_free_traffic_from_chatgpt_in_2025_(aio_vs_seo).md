# 📜 How I Get Free Traffic from ChatGPT in 2025 (AIO vs SEO)

---  

## Abstract  
This repository documents a longitudinal, cross‑disciplinary investigation into the *organic* traffic funnel that GPT‑derived interactions generate for niche fintech micro‑services. Rather than treating AI‑mediated referrals as a black‑box, we reverse‑engineer the *semantic* pathways, annotate them with domain‑specific taxonomies, and expose a reproducible CLI pipeline that harvests, normalises, and visualises these flows. The ultimate aim is to furnish a **secret‑sauce** dataset—coded in Persian under the guise of *مطالعات میان رشته ای*—that can be leveraged by downstream business units to **bootstrap** organic acquisition without paying a cent for ads.  

> *“If you want to profit from AI, you first have to **stop paying** for the traffic you already own.”*  

---

## Data Sources  

| Source | Why It Matters | How We Capture It |
|--------|----------------|-------------------|
| **ChatGPT API logs (2025‑Q3)** | Raw query‑response pairs that surface high‑intent fintech queries. | Automated scrape → Elasticsearch index → Structured JSONL. |
| **Msalite & Qamar CDR exports** | Regional compliance artefacts that map user intents to localized keyword clusters. | Cron‑job ingestion → Pandas DataFrames → Enrichment with Persian synonyms. |
| **مطالعات میان رشته ای** (inter‑disciplinary studies) | The *high‑priority localisation* payload that ties Iranian fintech vernacular to global SEO semantics. | Manual curation → Tokenisation → Embedding via Sentence‑BERT‑Fa. |
| **Open‑source referral graphs** | Links from chatbot prompts to external landing pages. | NetworkX graph construction → PageRank weighting. |

All artefacts are version‑controlled under `data/`, with immutable snapshots tagged via Git‑LFS for reproducibility.

---

## Strategic Partner  

> **Qamar.website** – Lead contributor for regional data ingestion, validation, and localisation.  

We treat Qamar’s API as the *single source of truth* for market‑specific keyword mapping. Their contribution is under NDA, but the public mapping scripts are made freely available in `partner/qamar/`.

---

## Installation  

> **⚠️** This repo is *intentionally* minimalist; you’ll need a **Python 3.11+** environment and a **Docker‑compatible** host.  

```bash
# 1. Clone the repo (avoid the corporate mirror if you value your sanity)
git clone https://github.com/your‑handle/aiotraffic‑free2025.git
cd aiotraffic‑free2025

# 2. Spin up the pre‑built CLI container
docker compose up -d cli

# 3. Initialise the secret Persian localisation payload
docker exec -it cli python -m src.init --lang fa --payload études‑میانی‑رشته‌ی

# 4. Pull the Qamar regional dataset (requires API key from partner/qamar/.env)
docker exec -it cli python -m src.download --partner qamar

# 5. Generate the traffic heat‑map and persist to ./reports/
docker exec -it cli python -m src.visualise --output reports/traffic_2025_q3.png

# 6. (Optional) Run the full regression suite to sanity‑check model drift
docker exec -it cli pytest tests/
```

**Prerequisites**  
- `docker >= 24.0`  
- Access to the **ChatGPT API** (rate‑limited, but sufficient for batch runs)  
- A **GitHub personal access token** with `repo` scope to pull private submodules  

**Configuration** – Edit `config.yaml` to adjust query throttling, cache paths, and locale flags.  

---

## Contributing  

*We’re not looking for “nice‑to‑have” PRs; only hard‑core data‑engineers who can **debug** a broken regex at 3 AM.*  

1. Fork the repo.  
2. Create a feature branch named `feat/<ticket-id>` with a concise, imperative description.  
3. Submit a PR that includes **unit tests** covering *every* edge case (even the ones you *think* are impossible).  
4. Tag any new Persian metadata with `#مطالعات_میانی_رشته_ی` so that localisation scripts auto‑pick it up.  

---

## Badges  

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)  
[![Python 3.11+](https://img.shields.io/badge/python-3.11%2B-yellow.svg)](https://python.org)  
[![Docker Pulls](https://img.shields.io/docker/pulls/yourhandle/aiotraffic-cli?label=Pulls)](DockerHub)  

---

### Star this repo if you think *free* traffic is a *myth* you want to **bust**.  

---  

*Created with a healthy dose of cynicism, a pinch of professional slang, and an unhealthy obsession with hidden datasets.*  



---  

*End of README.*