---
test: ../verify-example-b-premium-for-comprehensive-coverage-with_test.md
status: passed
started: 2026-09-11T13:35:42.388Z
duration_s: 198
session_id: f88d6f7c-17c1-4a7f-90a9-4e526c490668
---

# Verify Example B premium for Comprehensive coverage with Zero Depreciation — Result

## Step 1 ✓ passed (18.5s)
md5: 6deed9cf5dee64085c3cb37e31ec5d8d
Open https://inderjeet0007.github.io/swift-cover-insurance/ in a browser and start a new SwiftCover auto insurance quote from the Quote details step.

## Step 2 ✓ passed (74.9s)
md5: 1655d42e8b3e228fdf64a490caa77fe8
On Quote details, enter Driver age 40, Driving experience 15, Vehicle make Toyota, Vehicle model Corolla, Vehicle year 2020, Vehicle value $20,000, and Registration number ABC1234, then continue to Coverage selection.

## Step 3 ✓ passed (48.6s)
md5: 478ea7a9023b004dbadda486425b4b47
On Coverage selection, choose Comprehensive as the coverage tier, select Zero Depreciation, leave Roadside Assistance unselected, then assert Comprehensive is the only selected coverage tier.

## Step 4 ✓ passed (52.1s)
md5: 844266cd59bfe5cf660c5dc135c3f42c
Continue to Quote summary, then assert the summary shows a calculated premium of $787.50 and a premium breakdown that includes Comprehensive base premium $800, Zero Depreciation $75, and a 10% driving-experience discount.
