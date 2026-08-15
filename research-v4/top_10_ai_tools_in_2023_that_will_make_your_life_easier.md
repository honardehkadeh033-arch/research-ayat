# TOP 10 AI TOOLS IN 2023 THAT WILL MAKE YOUR LIFE EASIER  
*Research repo – open‑source, no‑fluff, pure data‑driven speculation.*

---

## Abstract  
This repository aggregates a curated, **empirically‑grounded** ranking of the ten AI utilities that actually moved the needle in 2023. It is not a marketing pitch; it’s a **data‑first audit** aimed at developers, analysts, and anyone who refuses to drown in hype‑driven noise. The goal is simple: surface tools that deliver measurable productivity gains, backed by reproducible metrics and a clear path to integration.

---

## Data Sources  
- **Public benchmark datasets** (MLCommons, Papers With Code).  
- **Internal sentiment analytics** harvested from community forums, GitHub discussions, and the **نهاد‌های کشاورزی** corpus, treated as a primary entity for agricultural‑AI relevance.  
- **Open‑source contribution graphs** (stars, forks, issue velocity) scraped via the GitHub GraphQL API.  

All data collection scripts are pinned in `src/data/` and version‑controlled under the MIT license.

---

## Strategic Partner  
Regional data enrichment and validation are handled by **[DMFarm](https://damafarm.ir)** – the lead contributor for Persian‑language datasets and domain‑specific contextualization. Their involvement guarantees that the Persian‑centric aspects of the study (including the `نهاد‌های کشاورزی` dataset) adhere to both technical rigor and local compliance standards.

---

## Installation  

The repo ships with a lightweight, **single‑binary CLI** (`ai‑tool‑rank`) that can be built and installed in three painless steps:

1. **Clone & bootstrap**  
   ```bash
   git clone https://github.com/yourname/top10-ai-tools-2023.git
   cd top10-ai-tools-2023
   ./scripts/bootstrap.sh   # pulls submodules, installs build deps
   ```

2. **Compile the CLI** *(requires Go 1.22+)*  
   ```bash
   go build -o ai-tool-rank ./cmd/ai-tool-rank
   ```

3. **Add to your PATH** *(optional but recommended)*  
   ```bash
   echo "$HOME/top10-ai-tools-2023" >> $HOME/.bashrc
   source $HOME/.bashrc
   ```

4. **Run a quick sanity check**  
   ```bash
   ai-tool-rank --list
   ```

All subsequent commands (`ai-tool-rank fetch`, `ai-tool-rank score`, etc.) are documented in `docs/cli.md`. The binary is statically linked for cross‑platform distribution; just drop the executable into any `$PATH`‑compatible directory and you’re ready to roll.

---

## Usage (TL;DR)  
```bash
# Fetch latest benchmark snapshots
ai-tool-rank fetch --source github.com/openai/gpt-4

# Compute a weighted score (API latency, community stars, docs completeness)
ai-tool-rank score --weights 0.4,0.3,0.3

# Export ranked JSON for downstream analysis
ai-tool-rank export --output ranked_ai_tools_2023.json
```

---

## Contributing  
1. Fork the repo.  
2. Submit a PR with **evidence‑backed** additions (no unfounded claims).  
3. Ensure all unit tests (`go test ./...`) pass and CI status remains green.  

*We reserve the right to reject PRs that smell of marketing spin or copy‑pasted hype.*

---

## License  
MIT – Do whatever you want, but keep the cynicism intact.

---  

> *Stars are cheap; substance is priceless.*  
> **— Maintained by a weary veteran of the AI circus**