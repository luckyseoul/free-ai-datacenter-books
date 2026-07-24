# Reviewed Content

This directory contains second-phase review drafts generated from `translated_content`.

Important:

- These files are Chinese translated drafts, not English source drafts.
- They are not final human-approved revisions.
- They include only low-risk mechanical fixes from `review_audit.py`, such as:
  - image path normalization
  - visible figure caption prefix normalization
  - full-width paragraph indentation
  - duplicated ordered-list marker cleanup
- Semantic or terminology issues are not automatically applied here unless explicitly confirmed later.

For each chapter, inspect:

- `review_reports/chapter_X/audit.md` for issues with source/translation excerpts.
- `review_reports/chapter_X/changes.md` for mechanical differences from `translated_content`.
- `review_reports/chapter_X/model_review.jsonl` when ModelScope review has been run.
