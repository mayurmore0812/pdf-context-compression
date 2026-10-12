# Data, pretrained assets and provenance

## Reference corpora

| Source | Role | Citation |
|---|---|---|
| BookSum | Narrative chapters paired with reference summaries | [Dataset](https://huggingface.co/datasets/kmfoda/booksum), [BookSum paper](https://arxiv.org/abs/2105.08209) |
| arXiv summarization | Scientific papers paired with reference abstracts | [Dataset](https://huggingface.co/datasets/ccdv/arxiv-summarization) |

The prototype samples these collections. It does not claim use of their complete populations. Document groups are kept together to reduce same-book/document overlap. Sentence caps and source filtering affect the evaluated material.

Greedy ROUGE creates approximate sentence-selection labels. Reference-summary overlap is a training signal, not a comprehensive ground truth for source fidelity or usefulness to a downstream language model. The task does not involve newly hand-labelled sentence importance.

## Pretrained assets

| Asset | Role | Source |
|---|---|---|
| BGE base English v1.5 | Frozen sentence embeddings | [BAAI model card](https://huggingface.co/BAAI/bge-base-en-v1.5) |
| BART large CNN | Shared pretrained rewriting | [Model card](https://huggingface.co/facebook/bart-large-cnn) |

The pretrained encoder and rewriter are not original models trained by this project. Their configuration, revision, training domain and licence are separate from the project-specific sentence selectors.

## Document inputs

Inference PDFs are supplied separately and may contain personal or proprietary content. They are not automatically used for training. No personal reports, reference corpus rows, private sharing links, PDF files or generated summaries are included in this release.

## Licence boundaries

BookSum's hosted metadata lists BSD-3-Clause. That label alone does not resolve all rights in underlying books and third-party reference summaries. The BGE and BART cards identify MIT licensing for their published assets. Exact corpus/document rights and downloaded revision terms remain specific to each source. No blanket redistribution permission for input PDFs is asserted.
