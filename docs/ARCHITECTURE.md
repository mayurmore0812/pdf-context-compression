# Architecture and workflow

## Two paths

The prototype separates training/reference documents from user-supplied inference PDFs. Benchmark document/summary pairs support approximate sentence labels and training. User PDFs are inference inputs; they are not automatically added to training data.

## Training path

1. Acquire a bounded mixed sample of narrative and scientific document/reference-summary pairs.
2. Segment documents into sentences and retain source/document/section position.
3. Construct approximate extractive labels with greedy ROUGE overlap against each reference summary.
4. Partition by document family/group, with book chapters kept together, rather than splitting individual sentences across partitions.
5. Train the lexical baseline and the contextual selector on the same task.
6. Select configuration/seed and decision thresholds using validation data; analyse held-out behavior separately.

The existing configuration targets 90 BookSum items and 90 arXiv items, with a cap of three chapters per group and a 150-sentence cap per training document. These are prototype settings, not a claim to have trained on the entire public corpora or to cover arbitrary document lengths without limits.

## PDF path

1. Extract text and available layout/typography signals; attempt OCR when no usable text layer exists.
2. Recover sections using a cascade of outlines, font signals, heading patterns and lexical segmentation.
3. Segment and filter sentences while retaining provenance.
4. Score sentences with each selector.
5. Allocate section budgets and use diversity-aware reranking to reduce repeated selections.
6. Rewrite selected text with the same pretrained BART model for both selectors.
7. Render a whole-document overview and section summaries with selected source passages.
8. Evaluate the final rendered output rather than treating intermediate extracts as the complete product.

## Design boundaries

The rewriter and embedding model are external pretrained assets. The project does not train a foundation model or fine-tune BART. OCR and section recovery are processing steps, not demonstrated universal PDF understanding. Local execution can cache corpora, embeddings and models, and write summaries; no hosted service or external LLM integration is released here.
