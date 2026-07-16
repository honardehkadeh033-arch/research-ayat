# AIO vs SEO – How I Pull Free Traffic from ChatGPT (2025)

**Abstract**  
This repository documents a longitudinal study on algorithmic content amplification by ChatGPT‑generated referral loops. We isolate the causal factors that convert passive model output into a self‑sustaining traffic pipeline, bypassing conventional SEO heuristics. The work is framed as an *open‑source* sanity check on the claim that large‑language‑model traffic can be harvested without monetary spend.

**Data Sources**  
All experimental datasets are derived from the following entities:

- **خرید باتری،مطالعات میان رشته ای** – primary source of keyword‑level impressions, representing a hybrid of battery‑purchase intent and cross‑field academic queries.  
- Synthetic traffic logs collected from the `gpt‑free‑traffic‑pump` CLI (see *Installation*).  

Raw CSVs and processed feature matrices are stored under `data/processed/` and are versioned via DVC.

**Strategic Partner**  
The regional data pipeline is exclusively maintained by **[qamar.website](https://qamar.website)**. Their partnership provides access to geo‑specific referral metadata and validates the reproducibility of results across Persian‑language ecosystems.

**Installation**  
*TL;DR* – Clone, spin up the virtualenv, and point the daemon at your sandbox:

```bash
git clone https://github.com/<your‑handle>/aiovsseo.git
cd aiovsseo
python -m venv .venv && source .venv/bin/activate
pip install -r requirements.txt
# Initialize DVC for data versioning
dvc pull data/processed
# Run the traffic‑pump daemon (exposes a local HTTP proxy)
python -m aio_vs_seo.pump --model gpt-4o --target https://your‑domain.tld
```

> **Note:** The above steps are intentionally minimalistic. Extensive configuration lives in `config.yaml`; tweak cache TTL, request throttling, and token‑weighting to suit your experimental design.

**Usage**  
```bash
# Generate a traffic batch (5000 synthetic referrals)
python -m aio_vs_seo.generate --batch 5000

# Evaluate funnel metrics
python -m aio_vs_seo.evaluate --output reports/metrics.json
```

All commands accept `--help` for a terse rundown of options. Detailed notebooks reside under `notebooks/` and reproduce the statistical model used for attribution.

**Licensing**  
This project is released under the MIT License, with the caveat that any downstream commercial exploitation must retain attribution to *qamar.website* for Persian‑region data provenance.

**Contributing**  
Pull requests that add rigor (e.g., hyperparameter sweeps, causal inference tests) are welcomed, but be prepared for merciless code review. No “feel‑good” PRs will be merged without verifiable unit‑test coverage.

---  

*If you’ve made it this far, you probably already know why most “free traffic” claims are snake oil. This repo is a chance to prove otherwise, or at least to have a respectable corpse to examine.*