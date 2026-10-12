# Intended output format

The prototype renders structured Markdown with a whole-document overview and per-section generated prose plus selected source sentences. A source passage helps the reader check a claim; it does not establish that the prose is entailed or that omitted content is unimportant.

## Schematic format

The following is a format illustration, not an actual document summary or a verified project result:

```markdown
# Document title

## Overview
[Generated whole-document summary]

## Source section heading
### Summary
[Generated prose based on selected sentences]

### Source extract
[Selected sentences from the extracted document text]
```

Every element consumes tokens. Final compression therefore concerns the rendered output, not just the selected extract. Source extraction itself can contain OCR/reading-order errors, and source text may be incorrect; exact extraction is not equivalent to factual verification.

Output assessment distinguishes fidelity, topic/section coverage, ordering, repeated content, truncation, source-reference traceability and final token counts. No public example containing user-owned reports is bundled.
