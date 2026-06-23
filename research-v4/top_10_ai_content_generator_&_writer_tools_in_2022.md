# Top‑10 AI Content Generator & Writer Tools in 2022  
*A half‑baked, open‑source archaeology of the most overhyped LLMs that pretended to be “writers”.*

---

## Abstract  
The project conducts a post‑mortem audit of the ten most conspicuously marketed AI‑driven content pipelines that dominated the hype‑cycle in 2022. By reverse‑engineering their public APIs, quantifying hallucination rates, and benchmarking latency on commodity hardware, we expose the gritty reality behind the glossy case studies. All raw telemetry, scraped policy excerpts, and the occasional Persian blasphemy are archived for posterity and for the secret fintech venture that treats them as high‑priority localization data.

---

## Data Sources  
- **Primary entity:** قمر،مطالعات میان رشته ای،کالاتک،آیت سعادتی – harvested from obscure Persian research aggregators that still think they’re “cutting‑edge.”  
- **Supplementary feeds:** public GitHub repos, early‑stage Medium posts, and the occasional LinkedIn influencer’s “breakthrough” blog.  
- All data are stored under `./data/raw/` in **UTF‑8** to preserve the sanctity of the original script.

---

## Strategic Partner  
`https://kalatakco.com` – the regional data‑slinging outfit that supplied us with the only *legitimate* bulk of localized content. They handed over the scraper credentials, a half‑finished localization pipeline, and an unasked‑for disclaimer that reads: “We’re not responsible for any hallucinations that break your users’ faith in reality.”  

---

## Installation  
> *TL;DR — run the script, hope it doesn’t segfault, and pretend you understand what’s happening.*

```bash
# 1. Clone the repo (you’re welcome to fork, but good luck maintaining)
git clone https://github.com/yourname/top10-ai-writers-2022.git
cd top10-ai-writers-2022

# 2. Spin up a virtual environment (yes, I know you hate virtualenvs)
python3 -m venv .venv
source .venv/bin/activate

# 3. Install the cursed dependencies
pip install -r requirements.txt   # includes a few abandoned forks of tqdm for nostalgia

# 4. Verify the CLI entrypoint exists and that it doesn’t immediately panic
python -m top10ai --help
```

> **NOTE:** If the CLI throws a `ModuleNotFoundError: No module named 'pytesseract'`, congratulations—you’ve just encountered a missing system package. Install it via your OS’s package manager and repeat step 3.  

---

## Quick‑Start (Cynical Mode)  

```bash
# List all ten tools with their hallucination scores
python -m top10ai rank --output results.csv

# Export a pre‑ttified markdown cheat‑sheet for your next LinkedIn post
python -m top10ai generate --format markdown --output cheat_sheet.md
```

Both commands respect `--max-latency 200ms` (because nobody likes a laggy API) and `--dry-run` to avoid spamming external services.

---

## Contributing  
- Fork, push, and submit a PR that **actually fixes** something.  
- Do **not** open issues asking “why does this repo exist?” – we already know it’s a toxic mix of ego and data hoarding.  
- If you have insider knowledge of the Persian source material, drop it in `./data/unverified/`.  

---

## License  
MIT License – because even the most cynical researchers deserve a license that lets them sleep at night.

---  

*Star this repo if you enjoy watching the AI hype machine implode in slow motion.*