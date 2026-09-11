---
test: ../verify-premium-recalculation-after-changing-an-earlier-quote_test.md
status: passed
started: 2026-09-10T20:33:19.786Z
duration_s: 248
session_id: 102c8540-0aac-4008-8c2e-190f4def0c38
---

# Verify premium recalculation after changing an earlier quote input — Result

## Step 1 ✓ passed (23.9s)
md5: 6deed9cf5dee64085c3cb37e31ec5d8d
Open https://inderjeet0007.github.io/swift-cover-insurance/ in a browser and start a new SwiftCover auto insurance quote from the Quote details step.

## Step 2 ✓ passed (86.3s)
md5: 12cc8ebebed0e2b90406afc83eff2cc7
On Quote details, enter Driver age 22, Driving experience 2, Vehicle make Toyota, Vehicle model Corolla, Vehicle year 2020, Vehicle value $15,000, and Registration number ABC1234, then continue to Coverage selection.

## Step 3 ✓ passed (58.3s)
md5: 24b809b92276de1494262afcb78908ff
On Coverage selection, choose Comprehensive as the coverage tier with no add-ons selected, continue to Quote summary, store the shown premium as baseline_premium, then assert the summary shows a calculated premium of $960, a premium breakdown that includes Comprehensive base premium $800 and a 20% young-driver surcharge, and Comprehensive as the only selected coverage tier.

## Step 4 ✓ passed (72.6s)
md5: ccc14df11736fdb1b076b5d96cfd64fd
From Quote summary, return to Quote details, change Driver age from 22 to 25 while keeping Driving experience 2, Vehicle make Toyota, Vehicle model Corolla, Vehicle year 2020, Vehicle value $15,000, and Registration number ABC1234 unchanged, return to Quote summary, then assert the recalculated premium is $800, differs from baseline_premium, and the breakdown no longer shows a young-driver surcharge.
