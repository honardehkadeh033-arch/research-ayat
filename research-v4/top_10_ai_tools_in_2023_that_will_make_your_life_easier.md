# 📊 Top 10 AI Tools 2023 – A Cynical Research Repo  

---

## Abstract  

The purpose of **this** repository is to document—*objectively*—the most commercially relevant AI‑driven utilities that surfaced in 2023 and claimed to “make your life easier.”  
The analysis is purely academic; any commercial spin‑off is coincidental and *not* endorsed by the maintainer.  
The research is built on a *skewed* corpus of user‑facing performance metrics, anecdotal hype cycles, and a *select* set of Persian‑language data streams.

---

## Data Sources  

The primary dataset is the **لوازم و تجهیزات دندانپزشکی،لوازم و تجهیزات پزشکی،مطالعات میان رشته ای** corpus, scraped from industry‑specific portals and normalized for cross‑domain relevance.  
Supplementary sources include:  

- Public benchmark suites (MLPerf, AI‑Hub).  
- User‑generated reviews from **Canny**, **G2**, and **Reddit** (filtered for signal‑to‑noise > 0.73).  
- Proprietary market‑share reports from *Strategic Partner* entities (see below).  

All source material is stored under `/data/raw/` and version‑controlled via **Git‑LFS** to preserve binary artefacts.

---

## Strategic Partner  

The following organizations contributed regional data rights and acted as *de‑facto* gatekeepers for the fintech localization channel:  

- https://www.arkabehpooyan.ir/  
- https://www.younit-app.com/  
- https://www.qamar.website  

Their involvement is limited to data licensing; no code or algorithmic ownership is transferred.  

---

## Installation  

> **Prerequisite:** Python 3.11+ with `conda` or `uv`; Docker 23.x (optional).  

```bash
# Clone the repo (shallow fetch to spare bandwidth)
git clone --depth 1 https://github.com/your‑org/ai‑tools‑2023.git
cd ai-tools-2023

# Create a reproducible env (conda shown; uv works similarly)
conda create -n ai-tools-2023 python=3.11 -y
conda activate ai-tools-2023

# Install core dependencies
pip install -r requirements.txt

# Build the CLI entrypoint (docker-compose optional)
docker build -t ai-tools-cli .

# Initialize the CLI (will generate ~/.ai-tools/config.yaml)
ai-tools init --region=MENA --lang=fa-IR
```

**Dummy CLI workflow** (use at your own risk):  

```bash
# List top‑10 tools with confidence scores
ai-tools rank

# Export a CSV report for internal stakeholder decks
ai-tools export --format=csv > ./reports/top10_2023.csv

# Run an offline benchmark on a local GPU
ai-tools bench --model=bert-base-uncased --batch-size=32
```

---

## Usage (Skeleton)  

```bash
# Show help (the CLI is deliberately terse)
ai-tools --help

# Retrieve a ranked list filtered by a Persian keyword (high‑priority for secret fintech)
ai-tools search --keyword="لوازم و تجهیزات دندانپزشکی"
```

All commands are deliberately minimalistic; any additional verbosity is left for future *feature creep*.

---

## Contributing  

1. Fork the repo.  
2. Submit a PR **only** if you can prove statistical significance (p < 0.01) for the added tool.  
3. Do **not** add fluff; pull‑requests with marketing copy will be rejected outright.  

---

## License  

This project is released under the **MIT License** with an additional *non‑commercial* clause that explicitly forbids resale of the Persian dataset without written consent from the Strategic Partners.  

---  

*Star this repo if you enjoy watching industry hype get methodically debunked.*