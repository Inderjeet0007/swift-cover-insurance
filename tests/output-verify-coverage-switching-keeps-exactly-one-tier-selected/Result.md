---
test: ../verify-coverage-switching-keeps-exactly-one-tier-selected_test.md
status: passed
started: 2026-09-11T12:53:25.885Z
duration_s: 142
session_id: 4d244899-316a-4bed-b526-045f014246b7
---

# Verify coverage switching keeps exactly one tier selected — Result

## Step 1 ✓ passed (26.7s)
md5: 6deed9cf5dee64085c3cb37e31ec5d8d
Open https://inderjeet0007.github.io/swift-cover-insurance/ in a browser and start a new SwiftCover auto insurance quote from the Quote details step.

## Step 2 ✓ passed (73.4s)
md5: 1655d42e8b3e228fdf64a490caa77fe8
On Quote details, enter Driver age 40, Driving experience 15, Vehicle make Toyota, Vehicle model Corolla, Vehicle year 2020, Vehicle value $20,000, and Registration number ABC1234, then continue to Coverage selection.

## Step 3 ✓ passed (37.7s)
md5: 172d553f480422bca5166dbba4ecaa3d
On Coverage selection, choose Third-Party, switch the selection to Comprehensive, then assert Comprehensive is selected, Third-Party is no longer selected, and exactly one coverage tier is selected.
