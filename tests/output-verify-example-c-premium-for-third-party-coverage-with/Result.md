---
test: ../verify-example-c-premium-for-third-party-coverage-with_test.md
status: passed
started: 2026-09-11T13:53:55.158Z
duration_s: 175
session_id: bbb2eed4-ea7c-4df0-a3ba-862f1b709437
---

# Verify Example C premium for Third-Party coverage with Roadside Assistance — Result

## Step 1 ✓ passed (20.2s)
md5: 6deed9cf5dee64085c3cb37e31ec5d8d
Open https://inderjeet0007.github.io/swift-cover-insurance/ in a browser and start a new SwiftCover auto insurance quote from the Quote details step.

## Step 2 ✓ passed (62.8s)
md5: 777ff21482adcaf4f74bfc1b3a8ebecf
On Quote details, enter Driver age 50, Driving experience 20, Vehicle make Toyota, Vehicle model Corolla, Vehicle year 2020, Vehicle value $15,000, and Registration number ABC1234, then continue to Coverage selection.

## Step 3 ✓ passed (49.9s)
md5: 829107b71d16d67f4a4405d33504b516
On Coverage selection, choose Third-Party as the coverage tier, select Roadside Assistance, leave Zero Depreciation unselected, then assert Third-Party is the only selected coverage tier.

## Step 4 ✓ passed (37.4s)
md5: 1d5e32ab8b3a3e80dcf4b791f6184d5c
Continue to Quote summary, then assert the summary shows a calculated premium of $486 and a premium breakdown that includes Third-Party base premium $500, Roadside Assistance $40, and a 10% driving-experience discount.
