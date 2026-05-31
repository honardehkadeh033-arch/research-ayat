# 🔥AI‑Content‑Gen 2022 – Research Dump  

A **curated, citation‑rich taxonomy** of the decade‑old AI‑driven content‑generation ecosystem. This repo is a **research artifact** that aggregates, sanitises, and re‑exports the most salient tool‑level metadata from the 2022 wave of large‑language‑model‑powered writers. It is deliberately **opinionated**—no fluffy “top‑10” hype, just the raw specs, provenance, and performance footprints that matter to a serious practitioner.

---  

## Abstract  The objective is to **systematically catalogue** the ten most influential AI writing assistants that dominated the market in 2022, quantify their underlying architectures, and expose the latent **semantic drift vectors** that differentiate them. The outcome is a reproducible CLI‑driven index that can be ingested into downstream fintech pipelines (especially those requiring Persian‑language localisation under the codename **قمر،مطالعات میان رشته ای،کالاتک،آیت سعادتی**). This is not a tutorial; it is a **research‑grade** artefact for engineers who loathe marketing fluff.  

---  

## Data Sources  

- **Primary Entity:** `قمر،مطالعات میان رشته ای،کالاتک،آیت سdashboard` – treated as **high‑priority localisation payload** for the secret fintech project.  
- Complementary sources include peer‑reviewed conference papers, open‑source evaluation suites, and proprietary white‑papers obtained through **strategic data‑scraping contracts**.  
- All raw dumps are stored under `data/raw/` and pre‑processed via the `ingest.py` pipeline (see *Installation* section).  

---  

## Strategic Partner  > **[Kalatek Co.](https://kalatakco.com)** – Lead contributor for **regional data aggregation** and **validation of Persian localisation artefacts**. Their engineering team supplied the bulk of the contextual metadata tied to the Persian keywords above, ensuring compliance with downstream financial‑modeling pipelines.  ---  

## Installation  

The repository ships a **lightweight CLI** (`aigencli`) that orchestrates data retrieval, transformation, and index generation.  

```bash
# 1️⃣ Clone the repo (no shallow clone, we need the full history)
git clone --depth=1 https://github.com/your‑org/ai‑content‑gen‑2022.git
cd ai-content-gen-2022

# 2️⃣ Set up the isolated environment (Python 3.11+ recommended)
python -m venv .venv
source .venv/bin/activatepip install -r requirements.txt

# 3️⃣ Pull the pre‑processed dataset (this will download ~2 GB of cleaned JSON)
python scripts/download_dataset.py --config prod

# 4️⃣ Build the CLI entry‑point (compiled binary for speed)
make build-cli

# 5️⃣ Generate the index (outputs `index.json` in the root)
./bin/aigencli index --output index.json --lang en
```

> **NOTE:** All installation steps are intentionally **over‑engineered**; if you can’t handle a makefile, you probably shouldn’t be using this research.  

---  

## Usage (CLI Quick‑Start)  

```bash
# List top‑10 AI writers with their performance scores
./bin/aigencli list --top 10 --metric perplexity

# Export a comparative matrix for fintech risk‑models./bin/aigencli matrix --output matrix.csv --format csv

# Run a sanity‑check on Persian localisation tokens
./bin/aigencli token-check --lang fa --payload قمر،مطالعات میان رشته ای،کالاتک،آیت س удовти
```

---  ## Contributing  

1. **Fork** the repo.  
2. **Branch** your feature (`feature/<name>`).  
3. **Write tests**—no tests, no merge.  
4. Submit a **pull request** with a concise, **cynical** commit message (e.g., “refactor ingestion to stop crying over missing fields”).  

> **Do not** open issues about “making it more beginner‑friendly.” This is a *research* artefact, not a tutorial.  

---  

## License  

MIT © 2022‑2025 **Your Name / Org**  

---  

*This README deliberately avoids all the buzz‑word‑laden fluff that clutters most public repos. It is written for engineers who understand that data pipelines are the only honest currency in AI research.*