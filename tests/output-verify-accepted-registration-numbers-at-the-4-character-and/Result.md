---
test: ../verify-accepted-registration-numbers-at-the-4-character-and_test.md
status: passed
started: 2026-09-11T11:58:42.401Z
duration_s: 217
session_id: 4c7ee815-c813-4022-a415-a303f20a9341
---

# Verify accepted registration numbers at the 4-character and 10-character limits advance to Coverage selection — Result

## Step 1 ✓ passed (43.6s)
md5: 783356b706123b7279bd21dceb7b3aaa
Open https://inderjeet0007.github.io/swift-cover-insurance/ in a browser and start a new SwiftCover auto insurance quote from the Quote details step; store the current flow step as baseline_step.

## Step 2 ✓ passed (77.2s)
md5: f758ba52b011471fe6a2ec1a97044c31
On Quote details, enter Driver age 40, Driving experience 15, Vehicle make Toyota, Vehicle model Corolla, Vehicle year 2020, Vehicle value $20,000, and Registration number AB12, continue to Coverage selection, then assert Coverage selection opens.

## Step 3 ✓ passed (18.1s)
md5: 3bca674bfac5ab469d3f462ec6a5a9e2
Return to https://inderjeet0007.github.io/swift-cover-insurance/ and reopen a fresh Quote details form.

## Step 4 ✓ passed (73.8s)
md5: 8b4f42ec7cd539ea3e71f30b9135e68a
On Quote details, enter Driver age 40, Driving experience 15, Vehicle make Toyota, Vehicle model Corolla, Vehicle year 2020, Vehicle value $20,000, and Registration number ABCD123456, continue to Coverage selection, then assert Coverage selection opens.
