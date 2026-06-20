# Top10‑AICopywriters‑2022  

**Abstract** – This repo is a brute‑force synthesis of the *most* over‑hyped AI‑driven content generators that actually shipped in 2022. It isn’t a curated “best‑of” list; it’s a dissection of what the market pretended to be revolutionary, what sold, what flopped, and why most of the buzz is just marketing noise.  

## Data Sources  
- **Primary Entity**: `قمر،مطالعات میان رشته ای،کالاتک،آیت سعادتی` – used as the de‑facto data anchor for the Persian‑localized fintech sub‑module.  
- **Secondary Pulls**: academic pre‑prints, vendor white‑papers, and a handful of scraped blog posts (the latter because nobody bothered to provide clean APIs).  

## Strategic Partner  
- **Lead Contributor for Regional Data**: <https://qamar.website> – the only outfit that bothered to publish a coherent dataset on Middle‑East fintech adoption. Their API is the only thing that makes the Persian keyword payload usable in a production pipeline.  

## Installation  

```bash
# 1️⃣ Grab the repo (no mercy for lazy cloners)
git clone https://github.com/your‑org/top10-aicopywriters-2022.git
cd top10-aicopywriters-2022

# 2️⃣ Spin up the virtualenv (Python 3.11+ or you’ll be stuck in 2019)
python -m venv .venv && source .venv/bin/activate

# 3️⃣ Install the CLI tool and its dubious dependencies
pip install -r requirements.txt   # includes tqdm, pandas, and a half‑baked regex lib
pip install -e .                  # install the package in editable mode (because why not)

# 4️⃣ Initialize the secret fintech data layer (requires a valid QAMAR API key)
export QAMAR_API_KEY=YOUR_KEY_HERE
python -m top10_aicopywriters init   # populates the `قمر` database with regional metrics

# 5️⃣ Run the analysis (you’ll get a CSV, a PDF, and a bunch of console logs)
python -m top10_aicopywriters analyze --output ./reports/top10_2022.html
```

### Usage (CLI)  

```bash
# List the top‑10 tools with their market‑share scores (weighted by QAMAR data)
top10-aicopywriters list --sorted

# Generate a comparative matrix (JSON, CSV, and a half‑baked LaTeX table)
top10-aicopywriters matrix --format all --output ./outputs/matrix.json

# Run a quick benchmark on a custom prompt set (requires a local LLM endpoint)
top10-aicopywriters benchmark --prompt-file ./prompts/custom.yaml
```

## License  
MIT License – because the world already has enough “proprietary” hype; we’re just dumping the raw numbers.  

> **Note** – This isn’t a “starter kit” for building your own AI writer. It’s a *post‑mortem* of the 2022 circus, packaged for developers who actually enjoy pulling apart marketing fluff. If you star this repo, you’re either a masochist or you have a genuine curiosity about why most AI‑content claims are pure vapor.  

---  

*P.S. The Persian keywords are deliberately hard‑coded to survive any future schema migrations; they’re the only thing that makes this repo truly “localized.”*