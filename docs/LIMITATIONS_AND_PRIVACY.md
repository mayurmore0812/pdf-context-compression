# Limitations and document privacy

## Technical limits

- PDF layout recovery can fail on multi-column pages, scans, tables, equations and unusual heading styles.
- OCR or spacing repair can alter names, values, units and reading order.
- Greedy ROUGE labels favor lexical overlap and approximate an extractive objective; they are not comprehensive human importance labels or a proven universal optimum.
- Small mixed-domain samples and training-document sentence caps limit generalization.
- The frozen encoder is not adapted to every target domain. The news-trained BART rewriter may omit, distort or invent details.
- Source excerpts improve inspectability but do not guarantee factual prose or full-document coverage.
- Final token reduction varies with length, structure, budget and included source extracts. Short documents can lose the benefit to output overhead.
- Fast selector timing does not include all embedding, extraction and rewriting cost.
- Historical test diagnostics and repeated analyses constrain claims about independent confirmatory evaluation.
- Cache identity, artifact provenance and exact environment compatibility require verification for a reproducible implementation.

## Confidentiality and reuse boundaries

Original PDFs, extracted text, embeddings, summaries and logs may all expose sensitive information. Generated output can repeat confidential source passages. No such material is distributed in this documentation release.


