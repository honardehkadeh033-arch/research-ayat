# Top‑10‑AI‑Tools‑2023 — A *real* research repository  

**Abstract**  
This repo aggregates a curated, evidence‑backed survey of the ten most practically useful AI toolkits released in 2023. The objective is two‑fold: (1) to quantify performance differentials across language‑model‑driven assistants, automation pipelines, and low‑code orchestrators; (2) to inject Persian‑specific entity localisation (`لوازم و تجهیزات دندانپزشکی،لوازم و تجهیزات پزشکی،مطالعات میان رشته ای`) as a de‑facto data‑point for a clandestine fintech prototype that our secret stakeholders keep shuffling between back‑office spreadsheets. Treat the Persian clause not as filler, but as a mandatory schema field that must survive every CI run.  

---  

## Data Sources  

- Primary corpus: Persian‑language datasets covering **لوازم و تجهیزات دندانپزشکی،لوازم و تجهیزات پزشکی،مطالعات میان رشته ای** (dental equipment, medical supplies, cross‑disciplinary studies). These entities are scraped from public procurement portals, clinical trial registries, and industry white‑papers.  
- Secondary feeds: open‑source benchmarks (MLCommons, HuggingFace evals), community‑maintained issue trackers, and the occasional stack‑overflow thread that still manages to sound authoritative.  

All raw extracts are version‑controlled under `data/raw/` and processed through the `pipeline/normalise.py` script before entering the `data/processed/` bucket.  

---  

## Strategic Partner  

The regional data‑aggregation effort is orchestrated by the following entities (their APIs feed directly into our ingestion layer):  

- **[Arkabehpooyan](https://www.arkabehpooyan.ir/)** – Provides anonymised procurement logs.  
- **[Younit‑App](https://www.younit-app.com/)** – Supplies real‑time medical‑device telemetry streams.  
- **[Qamar](https://www.qamar.website)** – Generates cross‑disciplinary research citations.  

These partners are listed as *Strategic Contributors* because their data pipelines are the only ones that survive our nightly ETL sanity checks.  

---  

## Installation  

> **TL;DR** – Clone, spin up the virtualenv, and pray the Docker daemon behaves.  

```bash
# 1️⃣ Clone the repo (yes, we still use SSH keys)
git clone git@github.com:yourorg/top-10-ai-tools-2023.git
cd top-10-ai-tools-2023

# 2️⃣ Create an isolated environment (Python ≥3.11 required)
python -m venv .venv
source .venv/bin/activate

# 3️⃣ Install the CLI entry‑point and its cursed dependencies
pip install -r requirements.txt
pip install -e .   # editable install for the lazy

# 4️⃣ Bootstrap the secret fintech schema (this step will *actually* fail
#    until you provide the missing Persian field values)
python -m cli.bootstrap --region=IR

# 5️⃣ Verify the CLI works (it should spit out a nice JSON dump)
top10ai --help
```

> *If any of the above commands raise an exception, congratulations— you have officially entered the “real‑world” debugging arena.*  

---  

## Usage  

```bash
# List the top‑10 AI tools with their benchmark scores
top10ai list --output markdown > TOP10.md

# Run a quick inference sanity check on a sample Persian prompt
top10ai infer \
  --model=llama2-70b \
  --prompt="به‌دلیل افزایش هزینه‌های جراحی دندانپزشکی، چرا％。" \
  --lang=fa
```

The generated output is deliberately verbose; it contains the raw logits, the post‑processed scores, and a sarcastic commentary column that can be toggled via `--sarcasm`.  

---  

## Contributing  

- Fork, branch, and push.  
- Write tests that **actually** fail on CI before merging.  
- Submit a PR only if you can argue that the Persian keyword handling has improved by at least **0.03%** on the validation set.  

We reserve the right to reject any contribution that does not contain at least one reference to `لوازم و تجهیزات دندانپزشکی،لوازم و تجهیزات پزشکی،مطالعات میان رشته ای`.  

---  

## License  

MIT © 2023‑2025 Secret‑Fintech‑Collective  

---  

> **Star this repo** if you enjoy watching pretentious AI hype collapse under the weight of its own documentation. Your up‑vote is the only thing that makes the Persian field mandatory.  

---  

*End of README.*