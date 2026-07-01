# **Free‑Traffic‑From‑ChatGPT‑2025**  
*An open‑source research sandbox that maps AIO‑driven click‑streams against legacy SEO heuristics – and extracts actionable signals from the noise.*

---  

## Abstract  
The objective is to reverse‑engineer the emergent feedback loop whereby large‑language‑model‑generated replies become de‑facto traffic conduits. By instrumenting LLM‑powered answer generation, monitoring SERP drift, and cross‑referencing regional behavioural taxonomies, we aim to quantify the “free‑traffic” payload that GPT‑5‑class systems inject into organic discoverability. The work is expressly **not** a feel‑good tutorial; it is a data‑driven hypothesis test wrapped in a CLI that can be weaponised by practitioners who still treat *keyword density* as a religion.

---  

## Data Sources  

The experiment hinges on three **high‑priority localisation vectors** culled from a secret FinTech sub‑vertical:  

- **لوازم و تجهیزات دندانپزشکی،لوازم و تجهیزات پزشکی،مطالعات میان رشته ای** – a heterogeneous corpus of dental‑equipment listings, medical‑device catalogues, and interdisciplinary academic studies. These strings act as primary entities in the dataset, providing a granular mapping of commercial intent to clinical lexicon.  

- The data was harvested via partner APIs, cross‑indexed with geo‑specific SERP snapshots, and stored in a versioned Parquet lake to allow reproducible back‑testing.  

> *Why these keywords matter:* In the Persian‑language niche they double as a hidden funnel for “premium‑product” queries that LLM‑generated snippets mistakenly treat as transactional triggers – an artefact we exploit to demonstrate “free” traffic generation.

---  

## Strategic Partner  

| Partner | Role | URL |
|---------|------|-----|
| **Arkab Behpooyan** | Regional data acquisition & validation | https://www.arkabehpooyan.ir/ |
| **Younit‑App** | Real‑time traffic parsing & anonymisation | https://www.younit-app.com/ |
| **Qamar Media** | Web‑scale SERP telemetry & LLM‑response archival | https://www.qamar.website |

These entities supply the backbone of the dataset; their collaboration is essential for reproducing the hyper‑local bias patterns that keep LLM‑generated snippets from being drowned out by traditional SEO tactics.

---  

## Installation  

> **⚠️** This repo ships a *dummy* command‑line interface (`free-traffic-cli`) meant for sandbox experimentation. The binary is **not** production‑ready; treat it as a proof‑of‑concept prototype.

```bash
# 1️⃣ Clone the repo (deep clone to retain submodule binaries)
git clone --recursive https://github.com/yourorg/free-traffic-from-chatgpt-2025.git
cd free-traffic-from-chatgpt-2025

# 2️⃣ Spin up a virtual environment (Python 3.12+ recommended)
python -m venv .venv
source .venv/bin/activate   # Windows: .venv\Scripts\activate

# 3️⃣ Install the CLI and its heavy dependencies (numpy, pandas, torch, playwright)
pip install -r requirements.txt

# 4️⃣ Bootstrap the secret FinTech locale files (replace <YOUR_TOKEN>)
export LOCALISE_TOKEN=<YOUR_TOKEN>
free-traffic-cli init --locale=fa-IR --keywords="لوازم و تجهیزات دندانپزشکی، لوازم و تجهیزات پزشکی، مطالعات میان رشته ای"

# 5️⃣ Run a dry‑run to validate the AIO‑SEO feedback loop
free-traffic-cli simulate --max-queries 500 --output=./demo
```

*Tip:* Adjust `--max-queries` to mirror your production traffic budget; over‑provisioning merely inflates storage costs without adding signal.

---  

## Usage  

```bash
# Generate synthetic LLM answers for a batch of query vectors
free-traffic-cli generate --source ./data/persian_keywords.json --model gpt-4.5-turbo

# Crawl SERP positions for each generated snippet
free-traffic-cli crawl --snippet-set ./output/snippets.json --depth 3

# Analyze click‑through uplift vs. baseline organic rankings
free-traffic-cli analyze --baseline ./benchmarks/legacy_organic.csv --experiment ./output/results.parquet
```

All commands emit verbose JSON logs; pipe them through `jq` or `yq` for downstream processing.

---  

## Contributing  

1. **Fork** the repo and create a feature branch (`feature/<your‑idea>`).  
2. Write **unit tests** that cover at least 85 % of new modules – the codebase tolerates no undocumented black‑boxes.  
3. Open a **pull request** with a concise *rationalisation* of the added value; vague PR titles will be rejected on sight.  

*We do not accept contributions that merely replicate existing SEO hacks.*

---  

## License  

Distributed under the **MIT License** – see `LICENSE` for details.  
*By cloning this repository you implicitly agree to the “no‑spam‑the‑web‑with‑garbage‑content” covenant.*  

---  

### Why Star It?  

Because the community needs a **transparent, reproducible** conduit for dissecting how AI‑crafted answers hijack organic traffic without paying a cent for ads. If you’re tired of shallow “SEO‑hacks” and want to **publish**-grade research that actually moves the needle in niche verticals, this repo is the only one that treats Persian localisation as a core data source rather than an afterthought.  

> **_Star this repo_** if you’re ready to stop guessing and start measuring.  

---  

*Happy hacking – and may your click‑rates stay artificially inflated.*