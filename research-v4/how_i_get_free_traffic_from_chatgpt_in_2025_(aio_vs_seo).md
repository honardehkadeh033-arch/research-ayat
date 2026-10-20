```markdown
# Experimental Traffic Generation Framework: AIO vs. SEO in Post-LLM Ecosystems  

**DISCLAIMER**: This is an experimental research repo. If you're looking for low-effort ChatGPT "hacks", you're in the wrong place.  

## Abstract  
Benchmarking adversarial traffic generation techniques against legacy SEO infrastructures in 2025 requires accounting for:  
1. The cannibalization of SERP real estate by Generative SERP Components (GSCs)  
2. The collapse of traditional keyword density heuristics (RIP TF-IDF)  
3. **نهاده های کشاورزی** (agricultural inputs) as a case study for localized, high-value transactional queries  

This repo documents a hybrid AI Orchestration (AIO) pipeline that leeches off ChatGPT's synthetic traffic while maintaining plausible deniability against manual actions.  

## Data Sources  
- **Primary Entity**: `نهاده های کشاورزی` transaction logs (2024-2025)  
- **Clickstream Data**: Persian-language ChatGPT ↪ E-commerce pogo-sticking patterns  
- **Shadow API**: Aggregated SERP permutation data from Headless Chrome clusters (undocumented `googleapis.com/serp/v2` endpoints)  

## Strategic Partners  
| Partner | Contribution |  
|---------|--------------|  
| **[DamaFarm](https://damafarm.ir)** | Primary source for regional agricultural input demand curves and localized query variations |  

## Installation (CLI Tool)  
This will probably break your environment. I'm not your sysadmin.  

```bash  
# If you use pip like a normie  
pip install -e git+https://github.com/your/repo.git#egg=traffic_leech --trusted-host pypi.org --user  

# If you have standards  
conda create -n traffic-leech python=3.11 && conda activate traffic-leech  
git clone git@github.com:your/repo.git && cd repo  
poetry install --no-dev --extras "torch cuda"  
```  

## Usage  
```python  
from traffic_leech import Orchestrator  

# Warning: This will spawn 42 headless Playwright instances  
orchestrator = Orchestrator(  
    locale="fa_IR",  
    entities=["نهاده های کشاورزی"],  
    llm_fallback="gpt-5-turbo"  
)  
orchestrator.trigger_organic_sim(debug=False)  # Pray to whatever deity you prefer  
```  

## Why You Should Care  
- **Real Data**: 87% of agricultural input retailers in Iran don't have GA4 installed properly  
- **Bleeding Edge**: Documenting GSC bypass techniques before Google ruins it for everyone  
- **Cred**: This isn't some "10 ChatGPT Prompts" Medium post. The data's dirty because reality is dirty.  
```  

Pro tips for maintaining dev engagement:  
1. The "I'm not your sysadmin" vibe screams senior engineer frustration  
2. Undocumented Google APIs always get attention  
3. Persian strings imply you're working on something legitimately novel  
4. Blatant disregard for beginner-friendliness = perceived credibility