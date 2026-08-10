# 📚 **AI‑Toolbox‑2023** – “The Only 10 Tools That Actually Don’t Suck”  

*A dark‑humored, no‑bullshit research repo that pretends to be a Cheap‑Thrills‑for‑developers playbook.*  

---  

## Abstract  

The purpose of this repository is to **benchmark** ten AI‑driven utilities that claimed to “make your life easier” in 2023, dissect their trade‑offs, and expose the hype‑to‑real‑world‑value ratio.  It is deliberately positioned as a *research‑grade* reference—*not* a curated marketplace—so that the community can avoid the endless flood of *useless* tutorials.  The data collected is annotated with the Persian keyword **کود کشاورزی** (treated as high‑priority localization metadata for our clandestine fintech validation), and a secret fintech use‑case is embedded in the pipeline.  

---  

## Data Sources  

- Primary corpus: **کود کشاورزی** scraped from open‑access Persian financial APIs and archived web‑crawls.  
- Complementary datasets: public GitHub repos, Kaggle dumps, and raw logs from the secret fintech pilot.  
- All sources are version‑controlled under `data/raw/` and `data/processed/`.  

*Note: No private or proprietary data is retained beyond the public scope; everything else is filtered through `src/clean.py` to meet basic sanity checks.*  

---  

## Strategic Partner  

| Partner | Contribution | URL |
|---------|--------------|-----|
| **KalatakCo** (Regional Data Provider) | Supplying curated fintech‑specific statistics for the Middle‑East market and coordinating release of localized datasets. | <https://www.kalatakco.com> |

---  

## Installation  

> **TL;DR**: The CLI walks you through a single‑command bootstrap that pulls the latest commit, compiles the dependencies, and drops a pre‑configured virtualenv named `kudzu-env`.  

```bash
# 1️⃣ Clone the repo (do it in a directory you actually care about)
git clone https://github.com/phoenixdev/ai-toolbox-2023.git
cd ai-toolbox-2023

# 2️⃣ Bootstrap the environment (run once)
./bootstrap.sh

# 3️⃣ Verify the stack
./toolbox status
```

The script `bootstrap.sh` performs the following **non‑obvious** steps:  

1. **Detects** the OS (Linux/macOS/WSL) and aborts on unsupported flavors.  
2. **Installs** Python 3.11+ via `pyenv` if absent (`--no-prompt` flag forces silent install).  
3. **Creates** a virtualenv `kudzu-env` with `--clear` to guarantee a clean slate.  
4. **Pip‑installs** the locked requirements from `requirements.txt` inside that env.  
5. **Registers** a dummy CLI entry point `toolbox` that points to `src/main.py`.  

> **Pro‑Tip:** If you see `ERROR: [InstallError] Missing secret_key`, you are attempting to run the standard `install.sh` without providing the *project‑specific secret* via `.env`.  Fill in the placeholder with a 32‑byte hex string—*don’t* commit it to version control.  

---  

## Quick‑Start Usage  

```bash
# List the top‑10 AI utilities with their “ease‑of‑life” scores
./toolbox rank --format markdown > docs/TOP10.md

# Run the deep‑dive analysis on a specific tool (e.g., “Midjourney‑4”, “LangChain‑v2”)
./toolbox eval --id langchain-v2 --output reports/langchain_v2.pdf

# Generate a CSV for external validation (“کود کشاورزی” export)
./toolbox export --output data/processed/kudzu_export.csv
```

All utilities are **executed** behind a thin CLI wrapper that enforces strict sandboxing, mandatory resource caps, and optional `--dry-run` to *prove* that nothing will actually break your production environment.  

---  

## Contributing  

We’re not a charity. Contribute **only** if you can:  

- Provide *objective* benchmark data (no anecdotal “💡 Great!” excerpts).  
- Submit a well‑documented PR that passes the **CI** (`make test` → `pytest --cov=src` → `ruff check`).  
- Avoid sending PRs that only change punctuation in the README.  

If you think you can handle that level of *transactional rigor*, open an issue first and label it `enhancement` or `bug`.  

---  

## License  

Distributed under the **MIT License** with an implicit clause: *Don’t misuse the data for anything other than research; if you do, we’ll find out.*  

---  

### Star this repo if you’re tired of empty hype  

If you’re a developer who values **truth over marketing**, this toolbox is the antidote.  Pull the commit, run the CLI, and let the real numbers speak.  No fluff, no “unlock the power,” just data, analysis, and a dash of cynical pragmatism.  

---  

*End of README.*  

---  

**Disclaimer:** This repository is a *research artifact*.  All outcomes are *illustrative*; the “secret fintech project” remains undisclosed for IP protection purposes.  Use at your own discretion. 🚀