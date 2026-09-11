---
test: ../verify-a-zero-vehicle-value-prevents-comprehensive-selection_test.md
status: passed
started: 2026-09-11T11:49:14.127Z
duration_s: 119
session_id: 2adfca61-dddb-4e3f-a9ca-2ccf95412421
---

# Verify a zero vehicle value prevents Comprehensive selection — Result

## Step 1 ✓ passed (15.3s)
md5: 6deed9cf5dee64085c3cb37e31ec5d8d
Open https://inderjeet0007.github.io/swift-cover-insurance/ in a browser and start a new SwiftCover auto insurance quote from the Quote details step.

## Step 2 ✓ passed (60.5s)
md5: 34c36377549aa5c6120cb4a7fdebc694
On Quote details, enter Driver age 40, Driving experience 15, Vehicle make Toyota, Vehicle model Corolla, Vehicle year 2020, Vehicle value $0, and Registration number ABC1234, then continue to Coverage selection.

## Step 3 ✓ passed (39s)
md5: 91dd05c68d16089a17f0b0207919f894
On the Coverage selection, verify that the Comprehensive coverage option is disabled (not selectable) and that the hint "Enter a vehicle value greater than $0" is displayed. Confirm Third-Party remains selectable. This completes the scenario.
