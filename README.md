# 🎯 JobScout — Program Management Job Aggregator

A production-ready static web dashboard consolidating jobs from LinkedIn, Naukri, Indeed, and IIM Jobs — with resume scanning and match scoring.

## Quick Start (no build required)

Open index.html directly in any browser. That is all.

## Project Structure

```
jobscout/
  index.html        — Main entry point (SPA)
  css/styles.css    — Full SaaS dashboard styling
  js/app.js         — App logic: filtering, rendering, modals, save/export
  js/resume.js      — Resume upload, parsing, match scoring engine
  data/jobs.js      — Job data: LinkedIn + Naukri + Indeed + IIM Jobs
  README.md         — This file
```

## Features

- Multi-source job aggregation: LinkedIn, Naukri, Indeed, IIM Jobs (toggle each)
- Sub-vertical chips: Program Mgmt, Brand Mgmt, Account Mgmt, Marketing Strategy, Growth, Category Mgmt, Digital Marketing, Portfolio Mgmt, Market Research
- Resume match engine: upload PDF/DOC/TXT, extracts skills, scores all jobs 0-100%
- Smart sorting: most recent, fewest applicants, best resume match
- Save jobs + export as CSV
- Full job detail modal with apply links
- Responsive: desktop, tablet, mobile

## Enable Live Apify Scraping

In js/app.js, find refreshJobs() and set:

```js
const APIFY_TOKEN = "your_apify_token_here";
```

Then uncomment the Apify fetch block. Actors used:
- LinkedIn: curious_coder/linkedin-jobs-scraper ($0.001/result)
- Indeed:   valig/indeed-jobs-scraper ($0.0001/result)

## Deploy to GitHub Pages

```
git init && git add . && git commit -m "init"
git remote add origin https://github.com/YOU/jobscout.git
git push -u origin main
# Repo > Settings > Pages > Source: main / root
```

## Deploy to Netlify

Drag the jobscout/ folder to netlify.com/drop — done.

## Deploy to Vercel

```
npm i -g vercel && vercel --prod
```

## Add More Jobs

Add entries to JOBS_DATA in data/jobs.js following the existing schema.
Source values: linkedin, naukri, indeed, iimjobs
Subvertical values: program_management, account_management, brand_management, marketing_strategy, market_research, growth_management, category_management, portfolio_management, digital_marketing

## License

MIT
