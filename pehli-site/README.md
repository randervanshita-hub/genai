# Pehli

A free two-minute Payday Plan: enter take-home pay and what is already committed, and get a Safe-to-Spend figure per week and per day, plus Two Cuts.

Student project for a course on generative AI. Not financial advice.

## What is in this folder

| File | What it does |
|---|---|
| `index.html` | The landing page and the Payday Plan form (one file: HTML, CSS and JavaScript). |
| `happy-1.jpg`, `happy-2.jpg`, `happy-3.jpg` | Optional photos for the "Saving feels better" section. If a file is missing the page shows a gradient card instead. AI-generated illustrations, not real customers. |
| `api/plan.js` | Vercel serverless function. Recalculates the plan, asks Gemini to write it, saves the exchange to Supabase, returns the answer. Enforces 300 output tokens and 5 plans per visitor per day. |
| `api/stats.js` | Vercel serverless function. Reads Supabase and returns "plans made" and "average saving identified" for the page. |
| `api/_shared.js` | The system prompt, the arithmetic and Supabase helpers used by both functions. |
| `supabase_setup.sql` | Creates the `pehli_plans` table. Run once in the Supabase SQL Editor. |

## Environment variables (set in Vercel, never in this repo)

- `GEMINI_API_KEY` from Google AI Studio
- `SUPABASE_URL` the project URL, e.g. `https://abcd1234.supabase.co`
- `SUPABASE_SERVICE_KEY` the Supabase secret (service role) key
- `GEMINI_MODEL` optional; the model name to use, copied from AI Studio

No API key appears in the page or in this repository.
