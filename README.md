# SwiftCover — Auto Insurance Quote &amp; Buy

A small, self-contained web app that models an **auto insurance quote-and-buy
flow**. It exists as a **test target** for TestMu AI Kane CLI's assurance and
evidence workflow — a realistic app with concrete, verifiable business rules that
browser tests can be designed against.

## Live app

Once GitHub Pages is enabled (Settings → Pages → deploy from `master`):

```
https://inderjeet0007.github.io/swift-cover-insurance/
```

This is the URL the Kane CLI tests run against.

## What it does

A four-step flow, completed in order:

1. **Details** — driver age, experience, vehicle make/model/year/value, registration.
2. **Coverage** — choose Third-Party or Comprehensive, add optional add-ons.
3. **Summary** — see the calculated premium with a full breakdown.
4. **Payment** — enter mock card details and receive a policy number.

No backend, no build step — a single `index.html` with inline CSS and JS.

## Business rules (acceptance criteria)

The app implements eight testable rules:

| ID | Rule |
|----|------|
| AC-1 | Drivers under 25 get a 20% surcharge. |
| AC-2 | Drivers with 5+ years' experience get a 10% discount. |
| AC-3 | Zero Depreciation add-on requires Comprehensive cover. |
| AC-4 | Comprehensive cover requires a vehicle value greater than $0. |
| AC-5 | Registration number is required and must be 4–10 alphanumeric characters. |
| AC-6 | Total discount never exceeds 20%. |
| AC-7 | Final premium never falls below $300. |
| AC-8 | A policy number is issued only after successful payment. |

### Worked examples

| Scenario | Premium |
|----------|---------|
| Age 22, 2 yrs exp, Comprehensive, no add-ons | $960.00 |
| Age 40, 15 yrs exp, Comprehensive + Zero Dep | $787.50 |
| Age 50, 20 yrs exp, Third-Party + Roadside | $486.00 |

## Testability

Every interactive element and error message carries a stable `data-testid`
attribute (for example `age`, `tier-comprehensive`, `continue-to-coverage`,
`policy-number`, `err-registration`). This gives the test-design step reliable
selectors instead of brittle text matching.

## Running locally

It's a static file — open `index.html` in a browser, or serve it:

```bash
npx serve .
# then open the printed localhost URL
```

## Purpose

This repository is a demonstration test target for an AI-assisted quality
engineering workflow. It is not a real insurance product; the payment step is
mocked and no data is stored or transmitted.
