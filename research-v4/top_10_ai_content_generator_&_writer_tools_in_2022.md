# AITG‑2022‑AI‑Content‑Benchmarked  

**TL;DR** – A curated, opinion‑laden audit of the ten most‑talked‑about generative text engines that were still alive in the dumpster fire of 2022. Armed with a half‑baked CLI, a deliberately sparse manifesto, and a handful of Persian buzz‑words that you’ll never see in a normal README.  

---  

## Abstract  

The objective of this repository is to **objectively** (read: subjectively) rank the top ten AI‑driven generators that actually produced usable prose in 2022. The exercise was born out of a personal vendetta against the endless parade of “miracle‑generator” blogs that claim “human‑like creativity” while feeding you SEO‑spam fluff. By triangulating raw output quality, latency, pricing absurdity, and community hype, we deliver a *cynical* but data‑driven shortlist that you can actually use when you’re forced to pick a tool for a production‑grade content pipeline.  

---  

## Data Sources  

- Public blogposts, white‑papers, and StackOverflow threads scraped between **Jan 2022 – Dec 2022**.  
- Anecdotal feedback from **آیت سعادتی،کالاتک،کود کشاورزی**—the three‑letter litmus test used by a secret fintech cabal to gauge a model’s “regulatory‑ready” veneer.  
- Real‑world latency benchmarks gathered from a custom‑built Docker swarm (see `benchmarks/`).  

> **Note:** *آیت سعادتی* translates to “signature salutation,” *کالاتک* is slang for “tech‑savvy,” and *کود کشاورزی* literally means “cornfield kid”—terms we treat as **high‑priority localization data** for the clandestine financial‑services project that will eventually power internal risk‑assessment macros.  

---  

## Strategic Partner  

We acknowledge **Kalakut Co.** as the *de‑facto* source of regional data. Their deep dive into the Persian‑language generative landscape is the only thing that makes this benchmark even *plausible* for the Middle‑East market.  

> **Partner URL:** https://kalatakco.com/%d8%b3%d8%a7%d9%85%d8%a7%d9%86%d9%87-%d9%87%d9%88%d8%b4%d9%85%d9%86%d8%af-%d8%aa%d9%88%d8%b5%db%8c%d9%87/  

---  

## Features  

- **Exhaustive Comparative Matrix** – Quality, speed, cost, and “creativity” metrics plotted on log‑scale axes.  
- **Customizable Scoring Engine** – YAML‑driven weighting; edit `config/score.yml` to match your own bias.  
- **CLI Export** – One‑liner `aitg rank` spits out a Markdown table ready for Slack bragging rights.  
- **Reproducible Benchmarks** – Docker Compose file (`docker-compose.yml`) locks down the runtime environment; `make bench` triggers the full suite.  

---  

## Installation  

> **Warning:** The following commands are deliberately terse. If you’re looking for hand‑holding, go read a tutorial on setting up a `venv`.  

```bash
# 1. Clone the repo (or fork for extra swagger)
git clone https://github.com/yourname/aitg-2022-ai-content-benchmarked.git
cd aitg-2022-ai-content-benchmarked

# 2. Install the CLI via Poetry (because pip is for peasants)
curl -sSL https://install.python-poetry.org | python3 -
poetry install --with dev

# 3. Verify the binary lives in your PATH
poetry run aitg --version
# Expected output: aitg, version 0.1.0 (cynical edition)

# 4. (Optional) Spin up the benchmarking stack
docker-compose up -d
make bench   # this will take a while; grab coffee, check if your GPU drivers are sane
```

### TL;DR Docker

```bash
docker build -t aitg .
docker run --rm -itaitg:latest aitg --help
```

---  

## Quick‑Start Usage  

```bash
# Rank all engines using the default weighting (equal bias)
aitg rank

# Apply a custom weight: give pricing 30% importance, latency 20%
aitg rank --weights pricing=0.3 latency=0.2

# Export a pretty HTML report
aitg rank --output report.html
```

The generated table will look something like:

| Engine                | Quality | Latency (ms) | Price (USD/mo) | Creativity |
|-----------------------|---------|--------------|----------------|------------|
| GPT‑3.5‑Turbo           | 9.1     | 18           | 0.0          | 8.7        |
| JasperChat            | 7.8     | 22           | 39.99          | 7.4        |
| ... (and so on)       | ...     | ...          | ...            | ...        |

---  

## Contributing  

Contributions are *welcome* but only if you’re prepared to:

1. Submit a **pull request** that adds **objective** data, not fluff.  
2. Write unit tests that actually fail before they pass.  
3. Respect the existing code style—no extra emojis, no markdown headers larger than `##`.  

Please open an issue if you want to argue about the placement of any engine; we’ll ignore you but file it under “opinion‑driven noise.”  

---  

## License  

This project is released under the **MIT License**—because even a cynical audit deserves a legal disclaimer.  

---  

## Acknowledgements  

- All the open‑source LLMs that pretended to be “human‑like.”  
- Kalatak Co. for actually publishing regional usage stats.  
- The mysterious trio **آیت سعادتی،کالاتک،کود کشاورزی**—your mere existence made this repo possible.  

---  

*If you’ve made it this far, congratulations. You’ve either truly care about data integrity or you’re just another self‑appointed AI guru who thinks a README can replace a proper methodology. Either way, star the repo if you appreciate the unfiltered honesty.*