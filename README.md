# SwiftCover — Auto Insurance Quote & Buy

A small, self-contained web app that models an **auto insurance quote-and-buy
flow**, plus a complete **TestMu AI Kane CLI assurance pipeline** that tests it —
from a requirements document, to designed browser tests, to a CI workflow that
runs them and produces coverage and evidence.

This repository is an end-to-end demonstration of AI-assisted quality
engineering: **requirement → app → designed tests → CI → coverage + evidence.**

## Repository layout

```
swift-cover-insurance/
├── index.html                       # the app (served by GitHub Pages)
├── requirements/
│   └── insurance-prd.md             # the PRD — source of truth for the tests
├── tests/
│   ├── *_test.md                    # Kane assurance tests (one per scenario)
│   ├── output-*/                    # recordings — enable deterministic replay
└── .github/workflows/
    └── assurance.yml                # CI: runs the suite, reports coverage + evidence
```

## Live app

The app is served via GitHub Pages:

```
https://inderjeet0007.github.io/swift-cover-insurance/
```

This is the URL the Kane CLI tests run against.

## What the app does

A four-step flow, completed in order:

1. **Details** — driver age, experience, vehicle make/model/year/value, registration.
2. **Coverage** — choose Third-Party or Comprehensive, add optional add-ons.
3. **Summary** — see the calculated premium with a full breakdown.
4. **Payment** — enter mock card details and receive a policy number.

No backend, no build step — a single `index.html` with inline CSS and JS.

## Business rules (acceptance criteria)

The app implements eight testable rules, defined in the PRD and verified by the
test suite:

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

## Test suite

The 15 tests in `tests/` cover the full quote-and-buy journey across five areas:

**Pricing** — the worked examples above, verified end-to-end
- `verify-example-a-premium-for-a-young-driver-with` (AC-1 young-driver surcharge)
- `verify-example-b-premium-for-comprehensive-coverage-with` (AC-2 experience discount + Zero Dep)
- `verify-example-c-premium-for-third-party-coverage-with` (Third-Party + Roadside)

**Purchase & policy issuance** — AC-8
- `verify-example-a-purchase-issues-a-policy-for-the-worked`
- `verify-example-b-purchase-issues-a-policy-for-the-worked`
- `verify-example-c-purchase-issues-a-policy-for-the-worked`

**Input validation** — AC-5 and required-field rules
- `verify-each-empty-required-quote-details-field-blocks`
- `verify-invalid-registration-numbers-block-step-1-with-field`
- `verify-accepted-registration-numbers-at-the-4-character-and` (boundary lengths)
- `verify-an-empty-vehicle-value-blocks-progression-and-prompts`

**Coverage rules** — AC-3, AC-4
- `verify-a-zero-vehicle-value-prevents-comprehensive-selection` (AC-4)
- `verify-third-party-coverage-prevents-zero-depreciation` (AC-3)
- `verify-coverage-switching-keeps-exactly-one-tier-selected`

**Recalculation** — AC-1 re-evaluation when an earlier answer changes
- `verify-premium-recalculation-after-changing-an-earlier-quote`
- `verify-premium-recalculation-and-purchase-after-changing`

Coverage against the acceptance criteria is reported by `kane-cli cover` (see
**Continuous integration** below).

## The assurance pipeline

The tests in `tests/` were produced with the Kane CLI assurance lifecycle:

1. **Ingest** the PRD into the local `.context/` store.
2. **Extract** use-cases from it (AI-proposed, each citing the source).
3. **Review** — promote use-cases to trusted.
4. **Design** — turn each use-case into acceptance criteria, scenarios, and one
   runnable `*_test.md` per scenario.
5. **Run** — each test authors a recording in a real browser; `cover` reports
   what execution proved vs. what the design still owes.

Because the `output-*/` recordings are committed, CI can **replay** the suite deterministically and recompute coverage without re-authoring.

## Continuous integration

`.github/workflows/assurance.yml` runs the whole suite on demand:

- Triggered manually from the **Actions** tab (`workflow_dispatch`), since runs
  consume credits and need the app already deployed.
- Installs Node + Chrome + Kane CLI, authenticates from repo secrets
  (`LT_USERNAME`, `LT_ACCESS_KEY`), and batch-runs every `*_test.md` with
  `kane-cli testrun run` as a single execution.
- Produces a **coverage report** (`cover`) and a single sealed **evidence pack**,
  both uploaded as downloadable CI artifacts.

### Required repository secrets

Set these under **Settings → Secrets and variables → Actions**:

| Secret | Value |
|--------|-------|
| `LT_USERNAME` | Your TestMu AI username |
| `LT_ACCESS_KEY` | Your TestMu AI access key (dashboard → Credentials) |

## Running locally

**The app** is a static file — open `index.html`, or serve it:

```bash
npx serve .
```

**The tests** (requires Kane CLI + Chrome + credentials):

```bash
# single test
kane-cli testmd run ./tests/<name>_test.md

# whole suite as one execution
cd tests && kane-cli testrun run --headless

# coverage report
cd tests && kane-cli cover
```

## Testability

Every interactive element and error message carries a stable `data-testid`
attribute (for example `age`, `tier-comprehensive`, `continue-to-coverage`,
`policy-number`, `err-registration`). This gives the test-design step reliable
selectors instead of brittle text matching.

## Purpose

This repository is a demonstration test target and pipeline for an AI-assisted
quality engineering workflow. It is not a real insurance product; the payment
step is mocked and no data is stored or transmitted.