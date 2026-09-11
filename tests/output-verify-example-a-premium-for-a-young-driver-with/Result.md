---
test: ../verify-example-a-premium-for-a-young-driver-with_test.md
status: passed
started: 2026-09-11T13:15:35.780Z
duration_s: 175
session_id: 04b4e75e-86bf-48ad-b376-9e5428fd9ef0
---

# Verify Example A premium for a young driver with Comprehensive coverage — Result

## Step 1 ✓ passed (26.8s)
md5: 6deed9cf5dee64085c3cb37e31ec5d8d
Open https://inderjeet0007.github.io/swift-cover-insurance/ in a browser and start a new SwiftCover auto insurance quote from the Quote details step.

## Step 2 ✓ passed (59s)
md5: 12cc8ebebed0e2b90406afc83eff2cc7
On Quote details, enter Driver age 22, Driving experience 2, Vehicle make Toyota, Vehicle model Corolla, Vehicle year 2020, Vehicle value $15,000, and Registration number ABC1234, then continue to Coverage selection.

## Step 3 ✓ passed (33s)
md5: c488c734071f70e13d4a2f0bd080a21f
On Coverage selection, choose Comprehensive as the coverage tier with no add-ons selected, then assert Comprehensive is the only selected coverage tier.

## Step 4 ✓ passed (51s)
md5: 8203a6665fc0248282824605b50ebc91
Continue to Quote summary, then assert the summary shows a calculated premium of $960 and a premium breakdown that includes Comprehensive base premium $800 and a 20% young-driver surcharge.
