# Model descriptions

## Model 1: lexical baseline

TF-IDF unigram/bigram features and eight positional/shape features feed Logistic Regression. This provides an interpretable sentence scorer and a comparison point for a more contextual representation. The learned task is imitation of approximate ROUGE-derived labels, not independent factuality judgment.

## Model 2: contextual selector

Frozen `BAAI/bge-base-en-v1.5` embeddings are combined with the same positional features. A bidirectional GRU processes each document's sentence sequence, followed by a small classification head. The source describes roughly 182,000 trained parameters in the contextual network; the much larger embedding encoder remains pretrained and frozen. Total system footprint also includes the encoder and rewriter.

The prototype includes a five-seed training comparison with validation-based selection. A selected seed's score should not be treated as expected performance across seeds. The public documentation does not designate a final winning model.

## Shared selection and rewriting

Both selectors feed section-aware budgets and Maximal Marginal Relevance-style diversity selection. `facebook/bart-large-cnn` rewrites selected text; it is shared, pretrained and not trained here. The checkpoint is adapted to news summarization, so narrative/technical inputs differ from its original task setting.

Classifier thresholds and selection budgets have different roles: a binary threshold controls classification metrics, while ranked/budgeted selection determines the extract supplied downstream. Good sentence-ranking scores do not alone establish factual final prose or downstream task success.

## Availability

This release documents the methods. It contains no model files, runnable inference code or reproducible installation environment. Pretrained assets are cited in [data and sources](DATA_AND_SOURCES.md).
