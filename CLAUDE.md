# Finances — Operating Playbook

Permanent personal finance ledger for Richard. **This file auto-loads when working in this
folder — follow it whenever you touch finances.**

## The golden rule
`finances.csv` is **append-only — NEVER delete or overwrite existing rows.** It is a permanent
historical record. Only add new rows (or fix an obvious typo in place). Answering a query must
never modify the data.

## Schema (finances.csv)
`Date,Type,Category,Description,Amount,Currency,Notes`
- **Date** — YYYY-MM-DD (transaction date; if Richard gives a whole-month figure, use the 1st)
- **Type** — Income | Expense
- **Category** — e.g. Rent, Groceries, Eating out, Transport, Subscriptions, Tuition, Fun, Savings
- **Description** — what it was
- **Amount** — positive number
- **Currency** — default USD (he's US-based at UMich; may use NZD when home in Auckland)
- **Notes** — anything

## Workflow
- When Richard reports finances, **append rows** to finances.csv and confirm what was added.
- For queries ("what did I spend June–Aug last year", "total on eating out this year"),
  **filter the ledger by date range / category and sum** — compute on the fly, never edit rows.
- Produce monthly or category rollups on request (computed, not stored — the ledger is truth).

## Durability
- Not yet in git. Offer to back it up to a private repo (like the body-and-mind one) so a
  permanent record isn't lost to a laptop wipe.
