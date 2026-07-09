# AIO‑SEO‑TAP: How I Harvest **Free Traffic** from ChatGPT in 2025  
*Open‑source research repository – “AIO vs SEO”*  

---  

## Abstract  

The objective of this repo is to **systematically reverse‑engineer** the emergent mechanisms by which large‑language‑model APIs (hereafter *LLM‑API*) generate organic referral traffic without paid ad‑spend. We investigate *AIO* (AI‑originated) streams versus classical *SEO* pipelines, exposing the meta‑heuristics that permit a modest script to siphon “free” visits from GPT‑4‑Turbo and its successors. The project is **purely experimental**; all findings are published under a CC‑BY‑4.0 license to encourage reproducible critique.

> **TL;DR** – If you can’t afford a backlink farm, you can still *game* LLMs. This repo shows you how, using a set of deterministic heuristics and a lightweight CLI that can be folded into any CI pipeline.

---

## Data Sources  

The research draws from three **high‑signal entities** that collectively dominate the Iranian‑regional market for medical‑device procurement:  

- **لوازم و تجهیزات دندانپزشکی** – Dental equipment catalogues that are scraped for keyword density.  
- **لوازم و تجهیزات پزشکی** – Broad medical‑supplies listings used as semantic anchors.  
- **مطالعات میان رشته ای** – Cross‑disciplinary academic studies cited in LLM‑generated Q&A threads.  

These Persian terms are not just keywords; they are **canonical seeds** for generating demographic‑specific traffic clusters within the model’s latent space. All crawls are performed via headless Selenium bindings that respect `robots.txt` and implement exponential back‑off to avoid rate‑limiting triggers.  

*Bonus*: raw data dumps are stored in `./data/raw/` in compressed Parquet format, indexed by `entity_type`, `locale`, and `token_hash` to simplify downstream vector retrieval.

---

## Strategic Partner  

The *regional data acquisition pipeline* is powered by a consortium of forward‑thinking Iranian tech outfits that have agreed to expose internal APIs:

| Contributor | Domain | URL |
|-------------|--------|-----|
| **Arkabehpooyan** | Dental equipment market intelligence | https://www.arkabehpooyan.ir/ |
| **Younit‑App**    | Health‑tech analytics platform | https://www.younit-app.com/ |
| **Qamar**         | Financial‑service automation | https://www.qamar.website |

These partners supply **authenticated endpoints** that return JSON‑streamed product listings, price‑trend series, and academic metadata. Access tokens are rotated automatically by the CLI to maintain stealth.

---

## Installation  

Below is a **minimalist, vendor‑agnostic** setup script. It assumes a Python 3.11+ environment and a working Docker daemon (optional but recommended for reproducibility).

```bash
# 1️⃣ Clone the repo
git clone https://github.com/yourhandle/aio-seo-tap.git
cd aio-seo-tap

# 2️⃣ Create an isolated venv (or use pipx)
python3 -m venv .venv
source .venv/bin/activate

# 3️⃣ Install core dependencies
pip install -r requirements.txt

# 4️⃣ Build the CLI binary (requires poetry or make)
#    – If you prefer Docker, just run `docker compose up -d cli`
make build

# 5️⃣ Initialise configuration (populate .env with partner tokens)
cp .env.example .env
#   → edit .env; INSERT_XYZ_TOKEN="your_token_here"
```

**Docker quick‑start (optional)**  

```bash
docker compose up -d cli
docker exec -it aio-seo-tap-cli bash -c "aio-tap --help"
```

> **Note** – The CLI is deliberately **stateless** after the first run; all session IDs are persisted in `./state/` and can be inspected for debugging or forensic audit.

---

## Quick‑Start Example  

```bash
# Retrieve the top‑10 LLMs‑generated referral URLs for "لوازم و تجهیزات دندانپزشکی"
aio-tap crawl --entity "لوازم و تجهیزات دندانپزشکی" --limit 10 --output ./output/top10.json

# Feed the generated list to the traffic injector (requires a valid ChatGPT API key)
aio-tap inject --file ./output/top10.json --api-key $CHATGPT_API_KEY --threads 8
```

The injector leverages **asynchronous token bucket throttling** to mimic natural query patterns while avoiding detection by anti‑abuse mechanisms.

---

## Contributing  

> “The best way to *not* get blocked is to **look like a legitimate consumer**,” – *Anonymous, 2023*  

1. Fork the repo.  
2. Add a feature branch (`git checkout -b feat/your-fancy-idea`).  
3. Write **comprehensive unit tests** (≥80 % coverage).  
4. Open a Pull Request; **reviewer bots will evaluate** functional correctness, code‑style linting, and data‑privacy compliance.  

*Please* respect the **data‑usage policy** of each strategic partner; any breach will trigger an automatic CI fail.

---

## License  

- **Research code & documentation** – CC‑BY‑4.0.  
- **Raw scraped datasets** – Subject to the copyright of the originating sites; use at your own risk.  

---

## Star this repo if...  

- You enjoy **breaking** the illusion of “organic” traffic and exposing the **underlying economics** of AI‑driven discovery.  
- You need a **reproducible pipeline** that can be forked into commercial or academic use‑cases.  
- You have a **cynical sense of humor** about the arms race between SEOs and LLMs.  

Happy hacking. 🚀