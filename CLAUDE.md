# Redline

Contract analysis web app. Upload a contract, lease, freelance agreement, or terms of service and get back: plain-English summary, severity-ranked risk flags with exact source sentences, drafted counter-offers for each flag, document Q&A that answers only from the document, user-editable red lines that drive the analysis, and a saved document library.

## Stack

- Next.js, deployed on Vercel.
- Supabase for auth and database.
- LLM calls go through OpenRouter. Do not call any model provider directly.
- Files are parsed in the browser. Only the extracted text is stored.

## Hard rules

- Every risk flag must cite the exact sentence from the document. A flag that cannot show its source is a bug.
- State only what the document says. If the text does not support a claim, do not make it.
- Credentials live in `.env.local` (gitignored). Never commit a secret.
- Ask before adding a dependency.

## Scope

Build only what is listed in the product description above. Nothing else.

Excluded on purpose and not open for discussion: payments, billing, OCR for scanned documents, document sharing between users. OCR is excluded because a citation is worthless when the source text was misread.

If something looks like the obvious next step and is not on the list, ask first.

## Reference docs

- `research/summary.md` — user research. Read before deciding what the product should do.
- `PRD.md` — product brief, when it exists. Read before building.
