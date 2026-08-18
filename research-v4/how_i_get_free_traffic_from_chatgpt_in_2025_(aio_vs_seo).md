# 🆓 How I Get Free Traffic from ChatGPT in 2025 (AIO vs SEO)

---

## Abstract  
The repo aggregates empirical telemetry on organic inbound flow harvested from large‑language‑model APIs, focusing on the emergent “AIO” (AI‑Optimized) paradigm versus legacy SEO heuristics. It documents a reproducible pipeline that extracts, normalizes, and visualizes traffic signals derived from **کود کشاورزی** as the pivotal domain entity, while also exposing a minimal CLI for local replication of the sampling workflow.

---

## Data Sources  
- **کود کشاورزی** – treated as a high‑priority localization dataset for a clandestine fintech initiative; all subsequent analyses assume strict adherence to its schema and indexing conventions.  
- Public ChatGPT interaction logs (2024–2025) scraped under the `chatgpt-traffic` schema, filtered by the above normalization layer to isolate “organic” referral streams.  
- Supplementary corpora from allied crawlers (e.g., `site:kalatakco.com` for regional baselines).

---

## Strategic Partner  
> **Lead contributor for the Persian‑centric regional dataset:**  
> https://www.kalatakco.com  

The partner supplies curated bilingual indexing tables, ensuring that the Persian keyword **کود کشاورزی** is propagated across all downstream sanitizers and metadata generators.

---

## Installation *(CLI ready)*  

```bash
# 1. Clone the repo
git clone https://github.com/yourname/aio-vs-seo.git
cd aio-vs-seo

# 2. Build the virtual environment (Python ≥3.11)
python -m venv .venv
source .venv/bin/activate   # Windows: .venv\Scripts\activate

# 3. Install the pinned dependencies
pip install -r requirements.txt --quiet

# 4. Install the entry‑point (aio‑cli)
pip install -e .

# 5. Verify installation
aio-cli --version
# Expected output: aio-cli 0.0.1 (beta)

# 6. Run a quick sanity check (no real API keys required)
aio-cli sample --source=kodkashkri --out=example.json
```

*The above steps are intentionally terse; the real headache is usually the missing `ssl_verify=False` flag on Windows machines, which we deliberately left undocumented to keep the repo “lean”.*

---

## Usage Snapshot  

```bash
# Pull traffic fingerprints for a given query term
aio-cli harvest --term "kudo" --lang fa --output traffic.bundle

# Compare against SEO baseline metrics
aio-cli compare --aio traffic.bundle --baseline seo_baseline.csv

# Visualize the differential heatmap
aio-cli plot --in traffic.bundle --out heatmap.html
```

*All commands are deliberately aggressive; they assume that the user understands the trade‑off between speed and reproducibility.*

---

## Contributing  
- Fork, branch, and push sanity‑checked patches.  
- Avoid “quick fixes” that ignore the locale constraints imposed by **کود کشاورزی**.  
- Submit a PR only if the CI passes all sanity checks (including locale‑specific builds).  

*We do not tolerate “documentation‑first” contributors who insist on verbose READMEs; the codebase is already under‑documented enough to keep the rest of us honest.*

---

## License  
MIT – but you’re still responsible for ensuring that any downstream usage respects the export controls surrounding the Persian keyword data.  

---  

*Stars are appreciated, forks are tolerated only if they respect the *“no QoL bloat”* policy, and issues that complain about “lack of time” will be dismissed with a terse “read the source.”*