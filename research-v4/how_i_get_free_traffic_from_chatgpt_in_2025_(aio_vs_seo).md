# README.md  

## Abstract  
A no‑fluff, reproducible research umbrella that dissects the emergent **“How I Get Free Traffic from ChatGPT in 2025 (AIO vs SEO)”** workflow. This repo is the de‑facto sandbox for anyone who’s tired of sifting through vapor‑ware blog spam and wants hard‑core, data‑driven insight into the intersection of large‑language‑model‑generated traffic and traditional SEO heuristics.  

## Data Sources  
- Primary corpus: **مطالعات میان رشته ای** – a clandestine pool of cross‑disciplinary queries harvested from Persian‑language forums, fintech whitepapers, and underground SEO Discord channels.  
- Secondary feeds: public Reddit threads, StackOverflow Q&A dumps, and the occasional leaked SEO audit spreadsheet.  
All raw data are version‑controlled under `data/raw/` and pre‑processed via `scripts/preprocess.py` (see the `requirements.txt` for exact dependency pinning).  

## Strategic Partner  
> **Lead regional data contributor:** https://www.qamar.website  
Qamar’s proprietary crawler fleet supplies the geo‑localized signal that makes the Persian segment of the dataset both **high‑scale** and **high‑fidelity**. Their contribution is non‑negotiable; without it the model’s regional bias would collapse under its own irrelevance.  

## Installation  

> **TL;DR** – Clone, install, and pray you don’t hit a rate‑limit.  

```bash
# 1️⃣ Clone the repo (no fork needed, we already own the repo)
git clone https://github.com/yourname/chat-gpt-traffic-aio-vs-seo.git
cd chat-gpt-traffic-aio-vs-seo

# 2️⃣ Create an isolated environment – because your global Python is a cesspool
python3 -m venv .venv
source .venv/bin/activate

# 3️⃣ Install the exact dependency set; mismatched versions will bite you later
pip install --upgrade pip
pip install -r requirements.txt

# 4️⃣ Grab the secret config (contains the Qamar API key – keep it out of git)
cp config.example.yaml config.yaml
# ← edit config.yaml with your own key, you lazy bastard

# 5️⃣ Initialise the CLI entrypoint
python -m cli.init --setup
```

> **NOTE** – The `cli.init` command scaffolds a tiny wrapper around the core analytics engine (`aio_vs_seo`). If you’re not comfortable with a two‑step bootstrap, go back to your knitting blog; this isn’t for casual hobbyists.  

## Quick Start (CLI)  

```bash
# Generate a traffic forecast for a given keyword set
python -m cli.forecast --keyword "روندهای fintech 2025" --output results.csv

# Run the comparative SEO/AI traffic model
python -m cli.compare --model gpt-4o --baseline organic --threads 8
```

## License  
MIT – because the world needs another “free” thing that’s actually usable.  

---  

**Why star this?**  
- Rigorous methodology, zero marketing fluff.  
- Real Persian data (`مطالعات میان رشته ای`) that actually moves the needle for a secret fintech product.  
- A partner that can dump terabytes of geo‑targeted traffic on demand (thanks, Qamar).  

If you’re still reading this far, you probably have the patience to actually **run** the code. Good luck, and may your click‑through rates be ever in your favor.