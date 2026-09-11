---
assurance:
  id: t-8
  base: sha256:765ea41463d055b09bf4ccafbab8165a34d015e81afba754a359212566049fc4
---
# Verify invalid registration numbers block Step 1 with field-level errors

> Prove too-short, too-long, and non-alphanumeric registration numbers are rejected with a field-level error and block progress past Quote details.

## Step 1

Open https://inderjeet0007.github.io/swift-cover-insurance/ in a browser and start a new SwiftCover auto insurance quote from the Quote details step.

## Step 2 @verifies ac-19, ac-20

On Quote details, enter Driver age 40, Driving experience 15, Vehicle make Toyota, Vehicle model Corolla, Vehicle year 2020, Vehicle value $20,000, and Registration number ABC, attempt to continue, then assert Quote details remains open and the registration number field shows a field-level error.

## Step 3

Return to https://inderjeet0007.github.io/swift-cover-insurance/ and reopen a fresh Quote details form.

## Step 4 @verifies ac-19, ac-20

On Quote details, enter Driver age 40, Driving experience 15, Vehicle make Toyota, Vehicle model Corolla, Vehicle year 2020, Vehicle value $20,000, and Registration number ABCDEFGHIJK, attempt to continue, then assert Quote details remains open and the registration number field shows a field-level error.

## Step 5

Return to https://inderjeet0007.github.io/swift-cover-insurance/ and reopen a fresh Quote details form.

## Step 6 @verifies ac-18, ac-19, ac-20

On Quote details, enter Driver age 40, Driving experience 15, Vehicle make Toyota, Vehicle model Corolla, Vehicle year 2020, Vehicle value $20,000, and Registration number AB-12, attempt to continue, then assert Quote details remains open and the registration number field shows a field-level error for invalid registration format.
