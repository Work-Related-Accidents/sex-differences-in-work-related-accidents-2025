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

## 3. Methodology

This repository implements an automated classification system for occupational data from workplace accidents using Large Language Models (LLMs). The methodology follows these key steps:

**1. Data Preprocessing**: Raw occupation titles from the ACHS (Chilean Work Safety Association) accident database are normalized by removing accents, standardizing punctuation, and converting to lowercase to ensure consistent classification.

**2. LLM-Based Classification**: We employ OpenAI's GPT-4o model to classify occupations according to the International Labour Organization (ILO) occupational classification system. The classification process uses a structured prompting approach:
- (a) system instructions define the task and classification rules, explicitly stating to avoid managerial classifications unless explicitly mentioned
- (b) the complete ILO taxonomy is provided as context in semicolon-separated format
- (c) each occupation title is processed individually with the query "What is the classification of the occupation {occupation}?" The model returns only the numeric classification code, ensuring consistent formatting for downstream analysis.

**3. Targeted Analysis**: We perform specialized classifications for two key occupational categories:
   - **Care Duties**: Healthcare, education, childcare, and domestic services (codes 221-235, 361, 531-532, 911-912)
   - **Manual and Machinery-Based Occupations**: Construction, manufacturing, transportation, and agricultural work (codes 72, 81, 83, 92, 93)

**4. Cross-Analysis**: The classified occupations are merged with accident mechanism data to analyze injury patterns by occupation type and sex, providing insights into workplace safety risks across different job categories.

This approach enabled the cross analysis between different data sources that consisted of free and unstructured text.