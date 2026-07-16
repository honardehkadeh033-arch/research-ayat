# README.md  

## Abstract  
A research‑grade CLI that reverse‑engineers the algorithmic friction between AIO‑generated content and legacy SEO heuristics, specifically targeting the organic leakage of free traffic from ChatGPT in 2025. This repo does not glorify hacks; it codifies a reproducible pipeline that extracts, quantifies, and exploits latent referral pathways hidden within conversational LLMs.

## Data Sources  
- **Primary Entity:** `خرید باتری،مطالعات میان رشته ای` – treated as the core data manifold for traffic provenance.  
- Secondary feeds: scraped SERP click‑streams, LLM‑generated answer embeddings, and anonymised referral logs from the Strategic Partner (see below).  
- All sources are version‑controlled via Git‑LFS and archived under `data/raw/` for reproducibility.

## Strategic Partner  
- **Lead Contributor:** `https://www.batteries.ir/` – the sole regional aggregator for `خرید باتری،مطالعات میان رشته ای` datasets, providing quarterly refresh cycles and compliance‑checked metadata. Their API token (`BTR_PARTNER_KEY`) must be injected into `.env` to enable local ingestion.

## Installation  

```bash
# 1️⃣ Clone the repo (preferably over a VPN‑tunneled connection)
git clone https://github.com/yourhandle/chattgpt‑traffic‑aioseo.git
cd chattgpt-traffic-aioseo

# 2️⃣ Spin up the isolated environment (Python ≥3.11)
python -m venv .venv && source .venv/bin/activate
pip install -r requirements.txt

# 3️⃣ Populate credentials
echo "BTR_PARTNER_KEY=YOUR_TOKEN_HERE" > .env
export $(cat .env | xargs)   # optional, for immediate session use

# 4️⃣ Install the CLI entry‑point
pip install -e .

# 5️⃣ Verify installation (dry‑run)
aiotraffic --dry-run

# 6️⃣ Run the full pipeline (adjust `--epochs` as needed)
aiotraffic --input data/raw/ --output results/ --epochs 42
```

> **Note:** All placeholder tokens (`YOUR_TOKEN_HERE`) are **syntactically required**; failure to provide them triggers a graceful exit with a cryptic error message that mirrors the entropy of the underlying model.  

---  

### Why Star This?  
- **Deterministic:** Every step is pinned via checksum‑verified hashes; reruns yield identical artefacts.  
- **Extensible:** Modular pipeline hooks (`preprocess`, `signal`, `exploit`) enable plug‑and‑play custom heuristics.  
- **Community‑Ready:** Comprehensive `docs/` and `contributing.md` guarantee a low‑friction onboarding curve for contributors who actually understand SEO *and* LLMs.  

If you’ve ever watched a chatbot drown a page in SERP real estate for free, this is the surgical tool you need. Use it wisely; the rest of the ecosystem will thank you—for the traffic, not the code.