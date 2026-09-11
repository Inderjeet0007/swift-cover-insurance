---
test: ../verify-third-party-coverage-prevents-zero-depreciation_test.md
status: passed
started: 2026-09-11T15:35:55.919Z
duration_s: 144
session_id: e762bbfa-5a52-4823-8d3a-6e02c6941852
---

# Verify Third-Party coverage prevents Zero Depreciation selection — Result

## Step 1 ✓ passed (19s)
md5: 6deed9cf5dee64085c3cb37e31ec5d8d
Open https://inderjeet0007.github.io/swift-cover-insurance/ in a browser and start a new SwiftCover auto insurance quote from the Quote details step.

## Step 2 ✓ passed (69.6s)
md5: 1655d42e8b3e228fdf64a490caa77fe8
On Quote details, enter Driver age 40, Driving experience 15, Vehicle make Toyota, Vehicle model Corolla, Vehicle year 2020, Vehicle value $20,000, and Registration number ABC1234, then continue to Coverage selection.

## Step 3 ✓ passed (50.1s)
md5: 23afdecc0c5db665de052b67c4081209
On Coverage selection, choose Third-Party as the coverage tier and try to choose Zero Depreciation, then assert Third-Party remains the only selected coverage tier and Zero Depreciation is not selectable.
