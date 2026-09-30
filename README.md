# NETA (Next-gen Enterprise Tracking & AI Analytics)

**AI visibility and accuracy monitoring for San Antonio small businesses**

**St. Philip's College** · 2026 HSI Battle of the Brains · Tech Submission `SPC_TECH_09302026`
Challenge Theme: *"The New Front Door: Trustworthy AI Product Discovery"*

### Live Demo: https://kieravarela99.github.io/SPC_TECH_09302026/

> **Judges:** No installation or login is needed. Open the link above and follow the
> [Judge Walkthrough](#judge-walkthrough). The demo is preloaded with a sample business and uses simulated data.

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
through search results, and AI-referred shoppers convert better than other visitors (Retailgentic, 2026).
If ChatGPT, Claude, or Gemini leaves a business out of its answer, or gets its prices, hours,
or services wrong, that business loses the customer and never finds out why. Large brands have
marketing teams and enterprise tools to track this. Local small businesses have nothing built for them.

## What NETA Does

NETA shows a small business **whether AI assistants mention it**, **whether what they say is true**,
and **what to fix**, with the owner approving every change.

| Module | What it does |
|---|---|
| **Visibility Monitor** | Runs realistic shopping questions (e.g., *"best pressure washing in San Antonio"*) through ChatGPT, Claude, and Gemini, and records whether the business is mentioned and which competitors appear instead. |
| **Accuracy Checker** | Compares what AI says about prices, hours, and services to the business's verified information, and ranks each error by priority so owners fix what costs them the most first. |
| **Fixes & Approval** | Suggests specific fixes, such as correcting a listed price. **Nothing changes until the owner approves it.** |
| **Local Event Checks** | Adds seasonal San Antonio questions for events like Fiesta, Día de los Muertos, Spurs games, and the holiday season, with an Event Readiness Score. |
| **Progress & History** | Tracks visibility and accuracy over time and keeps a history of every error found and every fix approved. |

The website also includes **How It Works**, a **Compare** page (NETA vs. Otterly, Peec AI, AthenaHQ, and Goodie), **Pricing** (Starter $49, Growth $99, Pro $199 per month), and **About** (mission, values, and team).

## Where AI Adds Value

NETA uses AI only where it clearly helps:

| Task | How AI is used | Why AI (instead of manual work) |
|---|---|---|
| Monitoring | Sends shopping questions to multiple AI assistants on a schedule | An owner cannot manually ask 3 assistants dozens of questions every week |
| Claim extraction | Turns a free-text AI answer into structured facts (price, hours, service) | AI answers are unstructured; extracting facts by hand is slow and error-prone |
| Fact validation | Compares extracted facts to the owner's verified information with a confidence score | Catches small wording differences a simple text match would miss |
| Fix drafting | Drafts plain-language website or listing updates | Owners without marketing staff get a ready-to-use starting point |

AI is **not** used to make final decisions. Publishing changes, confirming facts, and resolving
uncertain flags stay with a person.

## Ethics & Governance

### What happens automatically vs. what needs a person

| Automated by NETA | Requires Owner Approval | Never Performed by NETA |
|---|---|---|
| Runs scheduled visibility checks | Any change to website, listings, or service pages | Publish content on its own |
| Flags claims that conflict with verified info | Accepting a suggested fix | Write fake reviews or testimonials |
| Scores priority (e.g., wrong price = critical) | Editing the business's verified information | Make claims about competitors |
| Alerts the owner about critical issues | Resolving a low-confidence flag | Hide or delete history entries |
| Logs every check, flag, and decision | Submitting feedback to an AI provider | |

### Hallucination detection
1. **Repeat questions.** AI answers vary, so each question is run 3 times per assistant. An issue is flagged only if it repeats, which reduces false alarms.
2. **Extract claims.** Each answer is broken into individual factual claims.
3. **Compare to the source of truth.** Claims are checked against the owner's verified information.
4. **Confidence threshold.** Claims NETA cannot confidently match are sent for human review instead of being marked wrong.

### Accountability

| Who | Responsible for |
|---|---|
| **Business owner** | Keeping their verified information accurate; approving or skipping every change |
| **NETA Product Manager** | Detection quality; reviewing reported false flags and adjusting rules |
| **NETA CISO** | Protecting customer data and API keys; access control; the history log |
| **NETA Developer** | Fixing bugs and keeping integrations working when AI platforms change |

If NETA flags something incorrectly, the owner can mark it as not an issue. That feedback is
reviewed weekly by the Product Manager to improve detection.

### Keeping oversight working at scale
- **Priority-based alerts:** only critical issues trigger immediate alerts, so owners are not flooded.
- **Per-assistant tracking:** each AI assistant is measured separately, so new ones can be added without mixing results.
- **Sample audits:** each month, a person re-checks a random share of results NETA marked correct, to catch silent errors.
- **Full history:** every automated action and human decision is timestamped.

## Measuring Impact

| Metric | Definition | Shows |
|---|---|---|
| **Visibility** | Share of AI answers that mention the business | Visibility |
| **Accuracy** | Share of AI facts about the business that are correct | Customer trust |
| **Open Critical Issues** | Wrong prices, hours, or availability not yet fixed | Risk |
| **Time to Resolve** | Days from flag to approved fix | Governance working |
| **AI-Referred Customers** | Customers who found the business through an AI assistant, tracked with a "How did you hear about us?" question or tagged links | Conversion |

The Progress tab shows how visibility and accuracy change over time, so owners can see whether their updates helped.

## Tech Stack

| Layer | Technology |
|---|---|
| Frontend | HTML, CSS, JavaScript (single self-contained page) |
| Design | Claude Design (AI-assisted design tool), refined by our team |
| Hosting | GitHub Pages |
| Demo data | Simulated sample data built into the page |
| Production AI integrations (planned) | OpenAI API (ChatGPT), Anthropic API (Claude), Google Gemini API |

## Judge Walkthrough

The demo uses a sample business, **Alamo Pressure Pros**, a pressure washing company in San Antonio.

1. **Website pages:** Use the top menu to view **Home**, **How It Works**, **Compare**, **Pricing**, and **About**.
2. **Overview:** Open the demo dashboard to see how many AI answers mention the business and how many facts AI got right.
3. **Accuracy:** See each AI claim next to the verified fact, ranked by priority. Example: AI says deck cleaning costs $10, but it actually costs $1,000, flagged as **Critical**.
4. **Fixes:** Review a suggested fix and choose **Approve** or **Skip**. Nothing changes without the owner's approval.
5. **Events:** See upcoming San Antonio events and the business's Event Readiness Score.
6. **Progress:** See visibility and accuracy improving over time, plus a history of errors found and fixes approved.

## How to Run

### Option 1: Use the live demo (recommended)
Open **https://kieravarela99.github.io/SPC_TECH_09302026/**. Nothing needs to be installed.

### Option 2: Run locally
Requirements: Python 3.

```bash
git clone https://github.com/kieravarela99/SPC_TECH_09302026.git
cd SPC_TECH_09302026
chmod +x run.sh
./run.sh
```

Then open **http://localhost:8000** in your browser.

You can also simply double-click `index.html` to open it in any browser.

## Project Structure

```
SPC_TECH_09302026/
├── README.md     # this file
├── index.html    # the complete NETA website and demo dashboard
└── run.sh        # starts a local web server on port 8000
```

## Limitations & Next Steps

- **Simulated data.** This demo uses sample data. The production version would connect to the OpenAI, Anthropic, and Google Gemini APIs, which require API keys and usage costs.
- **AI answers vary.** The same question can get different answers, so NETA repeats questions and reports trends rather than single results.
- **API vs. consumer apps.** Answers from developer APIs may differ slightly from what shoppers see in consumer apps, so results are presented as close estimates.
- **AI platforms change often.** Each assistant connects through its own module, so one can be updated without affecting the others.
- **Next steps:** live API connections, Spanish-language checks, Google Business Profile integration, and more AI assistants.

## Originality

NETA was created by the St. Philip's College team for the 2026 HSI Battle of the Brains. The
interface was built with Claude Design, an AI-assisted design tool, and directed and refined by our team.
Third-party tools and sources are listed in the Tech Stack and References.

## References

AEO Labs. (2026). *Otterly.ai review (2026): Pricing, features, and limits.* https://www.aeolabs.ai/blog/otterly-ai-review

Anthropic. (2026). *Claude API documentation.* https://docs.claude.com

Goodie. (2026). *Pricing plans.* https://higoodie.com/pricing/

Google. (2026). *Gemini API documentation.* https://ai.google.dev

OpenAI. (2026). *OpenAI API documentation.* https://platform.openai.com/docs

Retailgentic. (2026, April 16). *Adobe releases Q1 AI traffic report and first-ever detailed retailer AI visibility data.* https://www.retailgentic.com/p/breakingadobe-releases-q1-ai-traffic

Ryze AI. (2026, August 29). *Peec AI review & pricing 2026.* https://www.get-ryze.ai/blog/peec-ai-review-pricing-2026

Trakkr. (2026). *AthenaHQ pricing in 2026.* https://trakkr.ai/reviews/athenahq-review/pricing
