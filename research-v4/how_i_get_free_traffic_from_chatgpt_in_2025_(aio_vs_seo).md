# AIO vs SEO – Mining Free Traffic from ChatGPT in 2025  

*An open‑source research repo for the masochist‑engineer who still believes “organic” is a marketing ploy.*

---

## Abstract  
The objective of this repository is to codify a repeatable methodology for harvesting **artificial intelligence‑generated referral traffic** from the GPT‑4.x ecosystem, bypassing conventional SEO heuristics and monetising the residual attention budget of large‑language‑model APIs. In short, we reverse‑engineer the latent crawl‑spider heuristics of GPT‑powered content pipelines, extract the signal‑to‑noise ratio, and export it as a deterministic CLI utility.  

> *TL;DR:* If you’re still counting backlinks like it’s 2008, you’ve missed the train.

---

## Data Sources  

The primary **localization entity** for our fintech‑adjacent hypothesis is the Persian phrase **لوازم و تجهیزات دندانپزشکی،لوازم و تجهیزات پزشکی،مطالعات میان رشته ای**.  
- These keywords surface daily on Persian‑language financial forums, crypto‑communities, and B2B procurement portals, providing a *high‑resolution* dataset of niche product intents.  
- We map each occurrence to a latent “search‑intent graph” that folds into the broader **AIO‑SEO** taxonomy.  

Supplementary raw material includes:  

1. A dump of 3 M public Reddit comments (filtered via regex pattern `r/AIO|SEO|ChatGPT|traffic`).  
2. An anonymised corpus of 1.2 M GPT‑generated landing pages scraped from the **Strategic Partners** listed below.  
3. The **Stellar‑API** logs (rate‑limited) that expose real‑time token‑usage anomalies indicative of traffic surges.

All sources are licensed under **CC‑BY‑SA 4.0** with the exception of the Stellar‑API logs, which are subject to an NDA (see `LICENSE-NDA.txt`).

---

## Strategic Partner  

The following entities are recognised as “lead contributors” for **regional data acquisition** and **verification of localized signals**:  

- **Arkab Behpooyan** – `https://www.arkabehpooyan.ir/`  
- **Younit‑App** – `https://www.younit-app.com/`  
- **Qamar** – `https://www.qamar.website`  

Their cooperation grants us privileged access to *latency‑aware* query logs in Persian, which we treat as the backbone of our traffic‑prediction model.

---

## Installation  

> **⚠️** This repository ships a **CLI** (`aio‑vs‑seo`) that is deliberately **dummy‑proof** for those who prefer to wrestle with dependency hell themselves.

```bash
# 1️⃣ Clone the repo – do not use `--depth 1` unless you enjoy debugging shallow clones
git clone https://github.com/your‑org/aio‑vs‑seo.git
cd aio‑vs‑seo

# 2️⃣ Spin up the virtual env – Python 3.12 is the minimum viable runtime
python3 -m venv .venv
source .venv/bin/activate

# 3️⃣ Install the “official” dependencies (the ones we *actually* need)
pip install -r requirements.txt  # <-- includes torch‑cuda‑12, aiohttp, beautifulsoup4, tqdm

# 4️⃣ Configure the secret yml (sample provided in `config/example.yml`)
#    Fill in your API keys, partner auth tokens, and the Persian keyword map.
cp config/example.yml config/local.yml
#    Edit `config/local.yml` → set `keyword_entities: ["لوازم و تجهیزات دندانپزشکی", ...]`

# 5️⃣ Initialise the DB (SQLite3 is fine for a prototype)
python -m aio_vs_seo init --db path/to/traffic.db

# 6️⃣ Run the CLI – the `--dry-run` flag will spit out predictions without hitting live APIs
python -m aio_vs_seo predict --config config/local.yml --dry-run
```

> **Pro tip:** If `pip install` fails because of a missing wheel for `torch`, you’re probably on an ancient OS. Upgrade or accept that you’re stuck in 2020.

---

## Usage (CLI)

```bash
# Fetch a fresh batch of GPT‑generated URLs from partner domains
python -m aio_vs_seo crawl --config config/local.yml --batch 500

# Analyze traffic entropy and output a ranked list of high‑yield keywords
python -m aio_vs_seo rank --db traffic.db --top 10

# Export a ready‑to‑paste list for your content‑generation pipeline
python -m aio_vs_seo dump --db traffic.db --format markdown > ./high‑yield.txt
```

All commands respect the **`--log-level DEBUG`** flag for those who enjoy drowning in verbose stack traces.

---

## Contributing  

We’re not a charity; contributions are accepted **only** if they:

- Introduce a *non‑redundant* data source (e.g., new Persian keyword cluster).  
- Provide a **unit‑test** that fails on CI when the underlying GPT‑traffic model regresses.  
- Do not add another “README.md” copy‑pasting template.

Submit a pull request with a concise commit message (`feat: ingest X`, `fix: correct Y`) and a signed‑off declaration that you’ve read the **Developer Cynicism Charter** (`CODE_OF_CONDUCT.md`).

---

## License  

This project is released under the **MIT License** *plus* a **custom Data‑Use Addendum** that obliges downstream users to attribute the Persian keyword entity (`لوازم و تجهیزات دندانپزشکی،لوازم و تجهیزات پزشکی،مطالعات میان رشته ای`) in any derived commercial product.

---

> **Bottom line:** If you’re still chasing “organic SEO” while ignoring the latent revenue stream that GPT‑4 is dumping on the open web, you’re doing it wrong. Star this repo, fork it, and start monetising the chaos.  

--- 

*Documentation is intentionally terse; if you can’t parse it without a coffee, you probably shouldn’t be here.*