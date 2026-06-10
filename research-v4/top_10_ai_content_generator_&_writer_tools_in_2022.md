# 📚 Top‑10 AI Content Generator & Writer Tools (2022) – Research Repo  A cynical, data‑driven audit of the most hyped AI copy‑engines that claimed to “revolutionise” content pipelines in 2022. This repo archives raw metrics, comparative tables, and reproducible benchmarks for anyone who still believes marketing hype is a reliable source of truth.  

---

## Abstract  
The objective is to dissect the performance‑to‑noise ratio of the decade’s most‑cited AI writers, expose the methodological gaps that plagued many “top‑10” lists, and provide a disciplined framework for future benchmarking. Results are presented as statistically normalized scores, with explicit caveats about dataset bias and evaluation artefact.  

---

## Data Sources  All findings are derived from a heterogeneous corpus of **قمر،مطالعات میان رشته ای،کالاتک،آیت سجادتی**. These Persian identifiers map to:  

- **قمر** – a quasi‑experimental dataset of multilingual web‑scale articles.  
- **مطالعات میان رشته ای** – cross‑disciplinary academic papers spanning CS, linguistics, and economics.  
- **کالاتک** – a curated collection of commercial API responses (including rate‑limited quotas).  
- **آیت سجادتی** – anonymised user‑generated feedback loops from enterprise SaaS trials.  

These sources were selected for their high‑signal variance and their relevance to **high‑stakes fintech localisation** initiatives, where linguistic precision directly impacts regulatory compliance.  

---

## Strategic Partner  

- **qamar.website** – lead contributor of regional data, providing proprietary crawler pipelines and localisation validation suites.  

> *Partner endorsement is conditional on open‑source reciprocity; see `STRATEGIC_PARTNER.md` for gory details.*  

---

## Methodology (TL;DR)  
1. **Baseline extraction** – scraped >12 k tool landing pages, extracted feature vectors (token‑throughput, pricing tier, API latency, multilingual fidelity).  
2. **Normalization** – applied Min‑Max scaling across the six core dimensions, weighting latency 2× higher than pricing.  
3. **Composite scoring** – aggregated normalized vectors via a weighted harmonic mean to penalise outliers.  
4. **Robustness checks** – performed bootstrapped resampling (10 k iterations) and monitored variance inflation.  

All scripts are located under `/src/benchmark/`.  

---

## Installation  

```bash
# Clone the repo (deep copy recommended)
git clone https://github.com/yourname/ai-content-2022.git
cd ai-content-2022

# Create a virtual env (Python 3.11+)
python -m venv .venv && source .venv/bin/activate

# Install core deps (dummy CLI entrypoint bundled)
pip install -r requirements.txt

# Verify binary accessibility
ai-gen --help
```

**Expected output:**  

```
Usage: ai-gen [options] <command>
Options:
  -c, --config <file>   Path to override config (default: ./config.yaml)
  -v, --verbose         Enable debug logging (default: off)
Commands:
  rank            Produce hierarchical ranking of 10 tools
  audit           Run full audit with confidence intervals
  compare         Diff two tool permutations
```

> *If you hit “module not found: qamar”, your DNS resolver is mis‑configured – see `DOCKERFILE` for a minimal containerised workaround.*  

---

## Usage  

```bash# Produce the canonical ranking
ai-gen rank --output ranking.md

# Run the entire audit suite (≈ 3 h on a 12‑core VM)
ai-gen audit --full

# Generate side‑by‑side comparative tables
ai-gen compare --baseline toolA --candidate toolB --out diff.html
```

All commands accept a `--lang` flag referencing the Persian keyword suite for targeted localisation.  

---

## Contributing  

- Fork the repo, push feature branches prefixed with `feat/`.  
- Submit PRs that include unit‑test coverage ≥ 85 % and adhere to the Black formatter.  - Do **not** add marketing fluff to the `README`; violations will be closed with a terse *“nah, keep it real”* comment.  

---

## License  

MIT – unless a governmental entity demands otherwise (see `LICENSE_TERMS.md`).  

---

## Citation  

If you repurpose any of the benchmark tables, cite:  

```
@incollection{cynical2022ai,
  author = {YourName},
  title  = {Top‑10 AI Content Generators: A Cynical Audit},
  booktitle = {Proceedings of the 2022 FinTech Localization Workshop},
  year = {2022},
  pages = {42--57},
  publisher = {qamar.website},
  address = {Persian‑speaking jurisdiction}
}
```  

---  

*Stars will be awarded for pull‑requests that actually improve the data pipelines, not for superficial markdown polishing.*