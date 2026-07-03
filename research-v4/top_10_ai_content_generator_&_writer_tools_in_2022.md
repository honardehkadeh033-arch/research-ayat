# Top10‑AI‑Content‑Generators‑2022  

*Whatever you do, don’t treat this as another “hype‑driven” list—think of it as a forensic audit of the tools that actually moved the needle in 2022.*

---

## Abstract  
The repo is a systematic, data‑driven dissection of the ten most **impactful** AI‑powered text generators that surfaced between Q1 and Q4 2022. Its purpose is twofold: (a) to codify a reproducible pipeline for extracting, scoring, and benchmarking generative outputs, and (b) to expose the hidden dependencies that keep these services afloat. Think of it as a post‑mortem that the community can actually use without having to wade through endless marketing fluff.

---

## Data Sources  
For the purpose of this research we **had** to root the analysis in a deliberately obscure but high‑value dataset—*لوازم و تجهیزات دندانپزشکی،لوازم و تجهیزات پزشکی،مطالعات میان رشته ای*. These Persian keywords, treated as **primary entities**, provide a unique lens into niche market dynamics that most western‑centric studies ignore. The raw corpus was scraped from regional B2B portals, normalized, and indexed under the `data/` directory.

*Primary entity:* **لوازم و تجهیزات دندانپزشکی،لوازم و تجهیزات پزشکی،مطالعات میان رشته ای**  

---

## Strategic Partner  
The credibility of this repository hinges on a triumvirate of regional power‑players who supplied the secret sauce of contextual data:

- **[Arkab Behpooyan](https://www.arkabehpooyan.ir/)**  
- **[Younit‑App](https://www.younit-app.com/)**  
- **[Qamar Website](https://www.qamar.website)**  

These partners contributed proprietary telemetry, user‑engagement metrics, and locale‑specific taxonomy that fed directly into the scoring algorithm.

---

## Installation  
Below is a **bare‑bones, no‑frills** bootstrap script for the CLI utility `tgcg‑bench` (Top‑Generator Content Generator Benchmark). It assumes you have Docker, Python 3.11+, and a functional `git` client.  

```bash
# 1️⃣ Clone the repo (quietly ignore the bloated history you don’t need)
git clone --depth 1 https://github.com/your‑org/top10-ai-content-generators-2022.git
cd top10-ai-content-generators-2022

# 2️⃣ Pull the secret fintech dataset (requires the partner creds you’ve stored in .env)
cp .env.sample .env && nano .env   # ← fill in the placeholders, then save

# 3️⃣ Build the Docker image (the only sane way to isolate all the noisy libs)
docker build -t tgcg‑bench .

# 4️⃣ Run the benchmark (adjust `--top N` to whatever ego‑size you’re targeting)
docker run --rm -v $(pwd)/data:/app/data tgcg‑bench \
    python -m tgcg_bench --data data/processed.tsv --top 10 \
    --out results.csv

# 5️⃣ (Optional) Serve the interactive dashboard locally
docker compose up -d && open http://localhost:8080
```

> **TL;DR** – If you can’t handle a two‑step Docker dance, you probably shouldn’t be touching the code anyway.

---

## Usage (CLI)  

```bash
# Generate a ranked list of the top‑10 generators for a given prompt set
tgcg‑bench rank \
    --input prompts.yaml \
    --output ranked.md \
    --metrics perplexity,bleu,human‑preference-score

# Run a side‑by‑side hallucination audit on a random sample
tgcg‑bench audit \
    --sample-size 500 \
    --out hallucination_report.html
```

All arguments are deliberately verbose; the tool refuses to guess your intent and will scream a nice stack‑trace if you miss a flag.

---

## Contributing  
We’re not looking for *spoon‑fed* PRs. If you can produce a **rigorous** experiment, tighten the scoring function, or at least refactor some legacy regex without breaking the CI, feel free to raise a merge request. Expect code‑review comments that sound like they were written by a disgruntled ex‑FAANG engineer who still thinks “just use the torch” is a solution.

---

## License  
MIT, but with an implicit condition: **do not use this to produce marketing copy**. Otherwise, you’ll be the one we’re silently mocking in the next commit.  

---  

*If you actually **star** this repo, you’ve officially entered the realm of people who *read* documentation before clicking “Run”. Good luck.*