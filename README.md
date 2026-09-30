<!--
  HOW TO USE THIS TEMPLATE (delete this comment box before submitting)
  - Replace everything in [square brackets] with your real details.
  - Delete any feature or section your app does not actually have. Judges will click around,
    so only describe what works.
  - Add screenshots: put image files in a /docs folder and replace the placeholder lines.
-->

# NETA — Next-gen Enterprise Tracking & AI Analytics

**AI visibility and accuracy monitoring for San Antonio small businesses**

**St. Philip's College** · 2026 HSI Battle of the Brains · Tech Submission `SPC_TECH_09302026`
Challenge Theme: *"The New Front Door: Trustworthy AI Product Discovery"*

### 🔗 Live Demo: [paste your Vercel/Netlify link here]

> **Judges:** No installation or login is needed. Open the link above and follow the
> [Judge Walkthrough](#judge-walkthrough). The demo is preloaded with a sample business.

| Team Member | Role |
|---|---|
| Kiera Varela | CEO |
| John Williams | CFO |
| Yaritza Cisneros Delgado | CISO |
| Dorothy Burrell | Product Manager |
| Anand Sukhlall | Developer / Software Engineer |
| Adeli Perez | Sales |

---

## Table of Contents
1. [The Problem](#the-problem)
2. [What NETA Does](#what-neta-does)
3. [Where AI Adds Value](#where-ai-adds-value)
4. [Ethics & Governance](#ethics--governance)
5. [Measuring Impact](#measuring-impact)
6. [Tech Stack](#tech-stack)
7. [Judge Walkthrough](#judge-walkthrough)
8. [How to Run](#how-to-run)
9. [Project Structure](#project-structure)
10. [Limitations & Next Steps](#limitations--next-steps)
11. [References](#references)

---

## The Problem

Shoppers increasingly ask AI assistants what to buy and where to buy it instead of clicking
through search results. If ChatGPT, Claude, or Gemini leaves a business out of its answer, or
gets its prices, hours, or products wrong, that business loses the customer and never finds out
why. Large brands have marketing teams and enterprise tools to track this. Local small
businesses have nothing built for them.

## What NETA Does

NETA is a web app that shows a small business **whether AI assistants mention it**, **whether
what they say is true**, and **what to fix**, with the owner approving every change.

| Module | What it does |
|---|---|
| **Visibility Monitor** | Runs realistic shopping questions (e.g., *"best bakery in San Antonio for quinceañera cakes"*) through ChatGPT, Claude, and Gemini, and records whether the business is mentioned, its position in the answer, and which competitors appear instead. |
| **Accuracy Checker** | Pulls factual claims out of each AI answer (prices, hours, products, availability, policies) and compares them to the business's verified **Fact Sheet**. Each claim is labeled ✅ Correct, ❌ Incorrect, ⚠️ Outdated, or ❔ Unverifiable, with a severity level. |
| **Source Insights** | Shows what information the AI appears to rely on (cited websites, review platforms, directory listings) and where those sources disagree with the business's own data. |
| **Recommendations & Approval Queue** | Drafts specific fixes (update a product page, add an FAQ, correct listed hours) and places them in a queue. **Nothing is changed until the owner clicks Approve.** Every decision is recorded in an audit log. |
| **Local Event Checks** | Adds seasonal San Antonio questions (e.g., Fiesta, Rodeo season) so businesses can see whether AI recommends them when local demand peaks. |
| **Trends Dashboard** | Tracks the visibility score and accuracy rate over time, so owners can see whether their updates helped. |

<!-- Delete rows for any module your demo does not include. -->

## Where AI Adds Value

The challenge asks teams to use AI only where it clearly helps. NETA uses AI for these tasks:

| Task | How AI is used | Why AI (instead of manual work) |
|---|---|---|
| Monitoring | Sends shopping prompts to multiple AI assistants on a schedule | An owner cannot manually ask 3 assistants dozens of questions every week |
| Claim extraction | An AI model turns a free-text answer into structured claims (price, hours, feature) | AI answers are unstructured text; extracting facts by hand is slow and error-prone |
| Fact validation | Compares extracted claims to the Fact Sheet and assigns a confidence score | Catches small wording differences a simple text match would miss |
| Fix drafting | Drafts plain-language website or listing updates | Owners without marketing staff get a ready-to-use starting point |

AI is **not** used to make final decisions. Publishing changes, confirming facts, and resolving
disputed flags stay with a person.

## Ethics & Governance

### What happens automatically vs. what needs a person

| ✅ NETA does automatically | 🧑 Requires owner approval first | 🚫 NETA never does |
|---|---|---|
| Runs scheduled visibility checks | Any change to website, listings, or product pages | Publish content on its own |
| Flags claims that conflict with the Fact Sheet | Accepting a drafted fix | Write fake reviews or testimonials |
| Scores severity (e.g., wrong price = high) | Editing or removing a fact on the Fact Sheet | Make claims about competitors |
| Alerts the owner about high-severity issues | Resolving a flag marked low-confidence | Hide or delete audit log entries |
| Logs every check, flag, and decision | Submitting feedback to an AI provider | |

### Hallucination detection
1. **Repeat questions.** AI answers vary, so each prompt is run [3] times per assistant. An issue
   is flagged only if it repeats, which reduces false alarms.
2. **Extract claims.** Each answer is broken into individual factual claims.
3. **Compare to the source of truth.** Claims are checked against the owner-verified Fact Sheet.
4. **Confidence threshold.** Claims NETA cannot confidently match are labeled *Unverifiable* and
   sent for human review instead of being marked wrong.

### Accountability

| Who | Responsible for |
|---|---|
| **Business owner** | Keeping the Fact Sheet accurate; approving or rejecting every change |
| **NETA Product Manager** | Detection quality; reviewing reported false flags and adjusting rules |
| **NETA CISO** | Protecting customer data and API keys; access control; the audit log |
| **NETA Developer** | Fixing bugs and keeping integrations working when AI platforms change |

If NETA flags something incorrectly, the owner marks it **"Not an issue."** That feedback is
logged and reviewed weekly by the Product Manager to improve detection.

### Keeping oversight working at scale
- **Severity-based routing:** only high-severity issues trigger alerts, so owners are not flooded.
- **Per-assistant tracking:** each AI assistant is measured separately, so a new one can be added
  without mixing results.
- **Sample audits:** a random share of "Correct" labels is re-checked by a person each month to
  catch silent errors.
- **Full audit trail:** every automated action and human decision is timestamped.

## Measuring Impact

| Metric | Definition | Shows |
|---|---|---|
| **AI Inclusion Rate** | % of shopping prompts where the business is mentioned | Visibility |
| **Average Position** | Where the business appears in AI answers (1st, 2nd, ...) | Visibility |
| **Accuracy Rate** | % of AI claims about the business that are correct | Customer trust |
| **Open High-Severity Issues** | Wrong prices, hours, or availability not yet fixed | Risk |
| **Time to Resolve** | Days from flag to approved fix | Governance working |
| **AI-Referred Customers** | Customers who say they found the business through an AI assistant (tracked with a "How did you hear about us?" field or tagged links) | Conversion |

The dashboard compares these numbers **before and after** each approved change, so owners
can see which updates improved results.

## Tech Stack

<!-- Replace with what you actually used. Delete rows you did not use. -->

| Layer | Technology |
|---|---|
| Frontend | [e.g., React / Next.js / HTML + CSS + JavaScript] |
| Styling | [e.g., Tailwind CSS] |
| Backend | [e.g., Next.js API routes / Node.js + Express / Python + Flask] |
| AI APIs | [OpenAI API (ChatGPT), Anthropic API (Claude), Google Gemini API] |
| Database | [e.g., Supabase / SQLite / JSON files for demo data] |
| Charts | [e.g., Chart.js / Recharts] |
| Hosting | [e.g., Vercel] |

## Judge Walkthrough

The live demo uses a sample business, **[Sample Business Name]**, a [type of business] in
San Antonio.

1. **Dashboard:** See the overall AI Visibility Score and Accuracy Rate at the top.
   `![Dashboard](docs/dashboard.png)`
2. **Visibility Monitor:** Click **[button/tab name]** to see which shopping questions were
   asked, which assistants mentioned the business, and which competitors appeared.
3. **Accuracy Checker:** Open **[tab name]** to see each AI claim next to the verified fact,
   with its label and severity. Try the flagged incorrect price as an example.
4. **Approval Queue:** Open **[tab name]**, review a drafted fix, and click **Approve** or
   **Reject**.
5. **Audit Log:** Open **[tab name]** to see your decision recorded with a timestamp.
6. **Trends:** Open **[tab name]** to see how visibility and accuracy changed over time.

<!-- If your demo can run a live check, add: "Click Run New Check to query the AI assistants in real time." -->

## How to Run

### Option 1: Use the live demo (recommended)
Open **[your hosted link]**. Nothing needs to be installed.

### Option 2: Run locally with one command
Requirements: [Node.js 20+ / Python 3.11+ / Docker].

```bash
git clone [your repo URL]
cd SPC_TECH_09302026
cp .env.example .env     # then paste your own API keys into .env
./run.sh
```

Then open **http://localhost:[3000]** in your browser.

### Environment variables
API keys are never stored in this repository. See `.env.example` for the list of required
variables:

```
OPENAI_API_KEY=your-openai-key-here
ANTHROPIC_API_KEY=your-anthropic-key-here
GEMINI_API_KEY=your-gemini-key-here
```

> Without API keys, the app runs in **demo mode** using saved sample results. <!-- Delete if not true. -->

## Project Structure

<!-- Replace with your real folders. In the terminal, `tree -L 2 -I node_modules` prints this for you. -->

```
SPC_TECH_09302026/
├── README.md
├── run.sh              # builds and starts the app
├── .env.example        # required environment variables (no real keys)
├── [src/]              # application code
├── [data/]             # sample business Fact Sheet and demo results
└── docs/               # screenshots used in this README
```

## Limitations & Next Steps

- **AI answers vary.** The same question can get different answers, so NETA repeats prompts and
  reports trends rather than single results.
- **API vs. consumer apps.** Answers from developer APIs may differ slightly from what shoppers
  see in the consumer apps. Future versions will add sampled checks of the consumer interfaces.
- **AI platforms change often.** Integrations are kept in separate modules so one can be updated
  without affecting the others.
- **Next steps:** Spanish-language prompts and interface, Google Business Profile integration,
  and more AI assistants (e.g., Perplexity).

## Originality

All code in this repository was written by the St. Philip's College team for the 2026 HSI
Battle of the Brains. Third-party libraries and APIs are listed in the Tech Stack and
References.

## References

<!-- Keep only the sources you actually used. -->

AEO Labs. (2026). *Otterly.ai review (2026): Pricing, features, and limits.* https://www.aeolabs.ai/blog/otterly-ai-review

Anthropic. (2026). *Claude API documentation.* https://docs.claude.com

Goodie. (2026). *Pricing plans.* https://higoodie.com/pricing/

Google. (2026). *Gemini API documentation.* https://ai.google.dev

OpenAI. (2026). *OpenAI API documentation.* https://platform.openai.com/docs

Retailgentic. (2026, April 16). *Adobe releases Q1 AI traffic report and first-ever detailed retailer AI visibility data.* https://www.retailgentic.com/p/breakingadobe-releases-q1-ai-traffic

Ryze AI. (2026, August 29). *Peec AI review & pricing 2026.* https://www.getryze.ai/blog/peec-ai-review-pricing-2026

Trakkr. (2026). *AthenaHQ pricing in 2026.* https://trakkr.ai/reviews/athenahqreview/pricing
