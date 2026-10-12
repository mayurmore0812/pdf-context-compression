# PDF Context Compression and Summarisation

> **Repository status:** README-only preview. The project pipeline and example outputs have not been published here yet (Code will be published soon after my project evaluation and marked by Professor).

## Approach

The notebook extracts PDF text and structure, segments sentences, and ranks content under a section budget. It compares a TF-IDF plus logistic-regression selector with a frozen sentence-embedding plus bidirectional-GRU selector. Both feed a pretrained BART rewriter, and the pipeline records token counts and source extracts. Evaluation includes sentence-selection metrics, ROUGE, calibration measures, and paired bootstrap analysis on the sampled corpus.

## Current limits

The saved experiments are based on a limited BookSum/arXiv sample and four example PDFs. Human claim verification and essential-point coverage were not completed. Some generated summaries need factual review, and the saved code includes downloads and file-writing steps.

## Planned release

I plan to add a system diagram, a cleaned canonical implementation, data and model provenance, reproducible evaluation tables, and one shareable example. 

**Tools used:** Python, PyTorch, scikit-learn, sentence embeddings, Hugging Face Transformers, PDF parsing.

**Code, models, and source documents are not yet available in this repository.**
