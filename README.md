# Sex differences in work-related accidents extracted from free text in Spanish using Natural Language Processing

This repository accompanies the paper **"Sex differences in work-related accidents extracted from free text in Spanish using Natural Language Processing"**.  It contains every notebook, utility script and (masked) dataset required to reproduce the quantitative results and visualisations reported in the manuscript.

## 1. Motivation
Analysing occupational accident reports is a key step toward safer workplaces.  However, incident descriptions are usually written as free text, making large-scale statistical analyses difficult.  Our study proposes an end-to-end Natural Language Processing (NLP) pipeline that automatically:

1. cleans and standardises raw Spanish accident descriptions,
2. assigns harmonised labels for occupation and accident mechanism, and
3. produces exploratory statistics that unveil sex-specific patterns.

## 2. Repository structure

| Path | Purpose |
|------|---------|
| `analysis/` | Jupyter notebooks that replicate every statistical analysis in the paper (age, geography, mechanisms, χ² tests, etc.). |
| `classification/` | NLP experiments.  The `llm.ipynb` notebook shows how Large Language Models were prompted/fine-tuned to label the data. |
| `data/` | Public artefacts required to run the notebooks.  Raw accident records are **NOT** included for privacy reasons. 

## 5. Citation
If you find this work useful, please cite:

## References

[https://doi.org/](https://doi.org/)

