# PANBIOME Book Project — Claude Context

## Project overview

Health/wellness non-fiction book by **Dr. Shibichakravarthy Kannan, MBBS, PhD** (Medical Geneticist & Diagnostics Specialist, Hyderabad). The book explains the human microbiome — gut, skin, oral, respiratory, vaginal — as a unified "Panbiome" ecosystem, drawing on South Indian, Mediterranean, and Okinawan dietary traditions.

**Publisher target:** Amazon KDP (Kindle + paperback)  
**Status:** Published on Amazon KDP (ASIN: `B0H592WT5G`), GitHub Pages landing page and recipe companion live with Buy Now links

---

## Key files

| File | Purpose |
|------|---------|
| `panbiome-book-all-chapters.txt` | **Master manuscript source** — all edits go here |
| `build_kindle_docx.py` | Converts source → `PANBIOME_KindleCreate.docx` |
| `PANBIOME_KindleCreate.docx` | Output for Kindle Create import (do not edit directly) |
| `index.html` | Book landing page with Amazon Buy Now buttons & overview |
| `PANBIOME_Recipe_Book.html` | Bonus 24-recipe companion with sticky buy navigation & upsell |
| `PANBIOME_Recipe_Book.md` | Markdown source for recipe book |
| `REVIEW_REPORT_v2.md` | Comprehensive fact-check report (29 issues, all fixed) |

---

## Active work context

**Phase:** Published & Live  
**Amazon KDP Listing:** `https://www.amazon.in/dp/B0H592WT5G` (ASIN: `B0H592WT5G`)  
**Worldwide / US Link:** `https://www.amazon.com/dp/B0H592WT5G`  
**GitHub Pages:** `https://musicofthings.github.io/panbiome/`  
**Latest completed:**
1. Published on Amazon KDP (Kindle & Paperback).
2. Updated `index.html` landing page with live publication badge, sticky navigation with Amazon Buy button, Kindle/Paperback format selection, and dedicated "Order Your Copy" showcase.
3. Updated `PANBIOME_Recipe_Book.html` with top-nav buy button, KDP publication banner, and comprehensive book showcase upsell card linking directly to Amazon.

---

## Manuscript structure

```
# PANBIOME
[title block — skipped by build script]
---
Author's Note (composite patient disclosure)
## PROLOGUE — The Invisible Organ
## INTRODUCTION
## Chapter 1–18
## EPILOGUE — Becoming a Better Host
## ABBREVIATIONS
## BIBLIOGRAPHY & REFERENCES
## ABOUT THE AUTHOR
  [Dedication section]
```

**18 chapters across 4 parts + 2 special chapters:**
- Part I (Ch 1–5): The hidden world, ecosystem, second brain, immunity, metabolism
- Part II (Ch 6–8): Modern lifestyle traps
- Part III (Ch 9–13): Action plan, gut reset, dashboard, mind-gut, supplements
- Part IV (Ch 14–16): Personalised medicine, next decade, Mediterranean/Okinawan traditions
- Special chapters (Ch 17–18): Female microbiome; First 1,000 days — written in **first-person doctor-narrator** voice (not the Priya-family vignette style) because the topics are sensitive. Sit between Ch 16 and the Epilogue.

---

## Build workflow

```bash
# Edit manuscript
nano "panbiome-book-all-chapters.txt"

# Rebuild DOCX
python3 build_kindle_docx.py
# → Saved: PANBIOME_KindleCreate.docx (862 paragraphs)

# Push recipe book updates
git add index.html PANBIOME_Recipe_Book.html
git commit -m "..."
git push
```

**Kindle Create import path:**  
File → Import → select `PANBIOME_KindleCreate.docx` → auto-detects Heading 1/2 styles → builds TOC → export `.kpf`

---

## Style conventions

- **British spelling** throughout (fibre, colour, organisation, practise)
- **Genus/species names** always italicised (*Lactobacillus*, *Akkermansia muciniphila*, *Prevotella*)
- **Inline markdown** in source: `**bold**`, `*italic*`, `***bold-italic***` — parsed by `build_kindle_docx.py`
- **Chapter headings** in source: `## Chapter N — Title` (mapped to Heading 1)
- **Sub-sections**: `### Sub-section` (Heading 2), `#### Deeper` (Heading 3)
- Do NOT use emoji in headings that should appear in TOC — strip before adding
- Composite patient vignettes — Priya is a composite; Author's Note already in front matter

---

## Key science facts (do not contradict)

| Claim | Correct version | Source |
|-------|----------------|--------|
| Microbe:human cell ratio | ~1:1 (≈38T bacteria, 30T human cells) | Sender et al., *Cell* 2016 |
| Microbial gene count | >100× human genes; ~3.3M microbial vs ~20K human | HMP, *Nature* 2012 |
| Gut serotonin | ~90% produced in gut; does NOT cross blood-brain barrier | Yano et al., *Cell* 2015 |
| Transplant study | Turnbaugh et al. (*Nature* 2006) + Ridaura et al. (*Science* 2013) | — |
| 30-plant weekly goal | American Gut Project / Tim Spector | McDonald et al., *mSystems* 2018 |
| Fucoidan → Akkermansia | Mechanistic evidence; human RCT data still limited (say "may support") | — |
| EVOO polyphenols | Olive oil quality varies widely; cold-press, low-heat | — |

---

## GitHub Pages

**Repo:** `https://github.com/musicofthings/panbiome`  
**Live URL:** `https://musicofthings.github.io/panbiome/`  
**Branch:** `main` — `index.html` = recipe book entry point  
**What's committed:** `index.html`, `PANBIOME_Recipe_Book.html`, `.gitignore`  
**What's gitignored:** manuscript source, DOCX, review reports, build script

---

## Author

**Dr. Shibichakravarthy Kannan, MBBS, PhD**  
Medical Geneticist & Diagnostics Specialist, Hyderabad, India  
Email: shibi.kannan@gmail.com  
KDP account: Indian publisher; British English spelling convention
