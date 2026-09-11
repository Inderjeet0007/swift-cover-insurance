---
test: ../verify-invalid-registration-numbers-block-step-1-with-field_test.md
status: passed
started: 2026-09-11T15:05:39.556Z
duration_s: 361
session_id: e1a0a7bd-5a97-4f15-b51d-36cf2585192b
---

# Verify invalid registration numbers block Step 1 with field-level errors — Result

## Step 1 ✓ passed (24.4s)
md5: 6deed9cf5dee64085c3cb37e31ec5d8d
Open https://inderjeet0007.github.io/swift-cover-insurance/ in a browser and start a new SwiftCover auto insurance quote from the Quote details step.

## Step 2 ✓ passed (97.2s)
md5: fbb604f17210c4d02cd61542c09ecbe3
On Quote details, enter Driver age 40, Driving experience 15, Vehicle make Toyota, Vehicle model Corolla, Vehicle year 2020, Vehicle value $20,000, and Registration number ABC, attempt to continue, then assert Registration Number input shows an error for invalid registration format.

## Step 3 ✓ passed (28.6s)
md5: 3bca674bfac5ab469d3f462ec6a5a9e2
Return to https://inderjeet0007.github.io/swift-cover-insurance/ and reopen a fresh Quote details form.

## Step 4 ✓ passed (83.8s)
md5: a1c09fae18d71da0153e9d9f2134e362
On Quote details, enter Driver age 40, Driving experience 15, Vehicle make Toyota, Vehicle model Corolla, Vehicle year 2020, Vehicle value $20,000, and Registration number ABCDEFGHIJK, attempt to continue, then assert Registration Number input shows an error for invalid registration format.

## Step 5 ✓ passed (23.9s)
md5: 3bca674bfac5ab469d3f462ec6a5a9e2
Return to https://inderjeet0007.github.io/swift-cover-insurance/ and reopen a fresh Quote details form.

## Step 6 ✓ passed (99.6s)
md5: 2313d5d217eabbe2d6b66d587235fdb9
On Quote details, enter Driver age 40, Driving experience 15, Vehicle make Toyota, Vehicle model Corolla, Vehicle year 2020, Vehicle value $20,000, and Registration number AB-12, attempt to continue, then assert Registration Number input shows an error for invalid registration format.
