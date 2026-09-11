---
assurance:
  id: t-10
  base: sha256:96ee3220a2fb53f9ae6f25ab35d0d3c9d5d2fd0b0adb41cad79f6217ce5b5dc8
---
# Verify accepted registration numbers at the 4-character and 10-character limits advance to Coverage selection

> Prove 4-character and 10-character alphanumeric registration numbers are accepted and allow progress past Quote details.

## Step 1

Open https://inderjeet0007.github.io/swift-cover-insurance/ in a browser and start a new SwiftCover auto insurance quote from the Quote details step; store the current flow step as baseline_step.

## Step 2 @verifies ac-16, ac-28

On Quote details, enter Driver age 40, Driving experience 15, Vehicle make Toyota, Vehicle model Corolla, Vehicle year 2020, Vehicle value $20,000, and Registration number AB12, continue to Coverage selection, then assert Coverage selection opens.

## Step 3

Return to https://inderjeet0007.github.io/swift-cover-insurance/ and reopen a fresh Quote details form.

## Step 4 @verifies ac-17, ac-29

On Quote details, enter Driver age 40, Driving experience 15, Vehicle make Toyota, Vehicle model Corolla, Vehicle year 2020, Vehicle value $20,000, and Registration number ABCD123456, continue to Coverage selection, then assert Coverage selection opens.
