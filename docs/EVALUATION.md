# Evaluation status and measurement definitions

**Status: evaluation in progress.** Preliminary experimental records exist. Final validated scores and reproducible benchmark conclusions are not part of this documentation release.

## Status by area

| Area | Prototype evidence | Public evaluation status |
|---|---|---|
| Sentence selection | Historical classification/ranking comparisons and simple baselines | Preliminary; no final winner asserted |
| Probability quality | Historical log-loss and Brier comparisons | Preliminary; ranking and calibration remain separate |
| Extractive summaries | Historical ROUGE comparisons | Reference overlap is not factuality validation |
| Rewritten summaries | Shared-rewriter comparisons and quality checks | Comprehensive factual support/coverage not established |
| Token compression | Per-document rendered-output counts | Document-dependent; no universal saving guaranteed |
| Uncertainty | Historical bootstrap/seed analyses | Final reporting and provenance review incomplete |
| Human review | Review is an evaluation objective | Completed factuality/coverage assessment not established |
| Downstream LLM tasks | Intended context-compression use case | Task-quality and monetary-saving validation not established |
| Reproducibility | Local experimental artifacts | Fresh public reproduction not available |

This table describes the project's evaluation stage, not a claim that a new evaluation run is currently executing.

## Measurement definitions

**Sentence selection:** precision, recall and F1 for the positive class; PR-AUC/average precision for ranking; ROC-AUC as a complementary measure. The positive-label rate determines the PR-AUC reference level. Approximate labels reflect greedy ROUGE reference overlap, not human-assessed importance.

**Probability quality:** log-loss and Brier score address calibration-related error. Ranking quality and calibrated probability estimates are different properties.

**Text quality:** ROUGE-1/2/Lsum measure reference overlap. Extractive selections and rewritten summaries are distinct evaluated outputs. ROUGE does not prove entailment, absence of invented claims or completeness of information.

**Compression:** token reduction is `1 - output_tokens / source_tokens`, with a specified tokenizer applied consistently. Output tokens include the entire rendered Markdown: overview, section prose, source extracts and headings. The extractive budget is not the same quantity as final token reduction.

**Efficiency:** end-to-end time includes extraction/OCR, section recovery, segmentation, embedding, selection, rewriting and export. Component timing is reported separately from total processing and from cold-download costs. Hardware, batch settings, cache state and dependency versions are necessary context.

**Context usefulness:** downstream task outcomes must be compared on full versus compressed context, using the same tasks and LLM settings. Token reduction alone does not establish retained task accuracy or monetary savings after compression compute is included.

## Interpretation boundaries

Document groups, sample sizes, truncation, genre, seed selection and historical reuse of evaluation data affect conclusions. Learning-curve/test diagnostics are distinct from a pristine confirmatory holdout. A reported metric difference does not establish a practically meaningful difference on unfamiliar documents.

No final accuracy, compression ratio, cost saving, speedup, superiority or hallucination-free claim is published here.
