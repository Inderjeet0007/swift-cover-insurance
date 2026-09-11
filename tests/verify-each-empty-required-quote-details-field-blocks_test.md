---
assurance:
  id: t-9
  base: sha256:20d466fee31e5a2c584507b22447219eefca3be7c2faea24c86682c8135d4ac4
---
# Verify each empty required Quote details field blocks progress with a field-level error

> Prove each required Step 1 field, when left empty, blocks progress and shows a field-level error.

## Step 1

Open https://inderjeet0007.github.io/swift-cover-insurance/ in a browser and start a new SwiftCover auto insurance quote from the Quote details step.

## Step 2 @verifies ac-21, ac-22

On Quote details, leave Driver age empty while entering Driving experience 15, Vehicle make Toyota, Vehicle model Corolla, Vehicle year 2020, Vehicle value $20,000, and Registration number ABC1234, attempt to continue, then assert Quote details remains open and the Driver age field shows a field-level error.

## Step 3

Return to https://inderjeet0007.github.io/swift-cover-insurance/ and reopen a fresh Quote details form.

## Step 4 @verifies ac-21, ac-22

On Quote details, enter Driver age 40, leave Driving experience empty, enter Vehicle make Toyota, Vehicle model Corolla, Vehicle year 2020, Vehicle value $20,000, and Registration number ABC1234, attempt to continue, then assert Quote details remains open and the Driving experience field shows a field-level error.

## Step 5

Return to https://inderjeet0007.github.io/swift-cover-insurance/ and reopen a fresh Quote details form.

## Step 6 @verifies ac-21, ac-22

On Quote details, enter Driver age 40, Driving experience 15, leave Vehicle make empty, enter Vehicle model Corolla, Vehicle year 2020, Vehicle value $20,000, and Registration number ABC1234, attempt to continue, then assert Quote details remains open and the Vehicle make field shows a field-level error.

## Step 7

Return to https://inderjeet0007.github.io/swift-cover-insurance/ and reopen a fresh Quote details form.

## Step 8 @verifies ac-21, ac-22

On Quote details, enter Driver age 40, Driving experience 15, Vehicle make Toyota, leave Vehicle model empty, enter Vehicle year 2020, Vehicle value $20,000, and Registration number ABC1234, attempt to continue, then assert Quote details remains open and the Vehicle model field shows a field-level error.

## Step 9

Return to https://inderjeet0007.github.io/swift-cover-insurance/ and reopen a fresh Quote details form.

## Step 10 @verifies ac-21, ac-22

On Quote details, enter Driver age 40, Driving experience 15, Vehicle make Toyota, Vehicle model Corolla, leave Vehicle year empty, enter Vehicle value $20,000, and Registration number ABC1234, attempt to continue, then assert Quote details remains open and the Vehicle year field shows a field-level error.

## Step 11

Return to https://inderjeet0007.github.io/swift-cover-insurance/ and reopen a fresh Quote details form.

## Step 12 @verifies ac-21, ac-22

On Quote details, enter Driver age 40, Driving experience 15, Vehicle make Toyota, Vehicle model Corolla, Vehicle year 2020, leave Vehicle value empty, and enter Registration number ABC1234, attempt to continue, then assert Quote details remains open and the Vehicle value field shows a field-level error.

## Step 13

Return to https://inderjeet0007.github.io/swift-cover-insurance/ and reopen a fresh Quote details form.

## Step 14 @verifies ac-19, ac-20, ac-21, ac-22

On Quote details, enter Driver age 40, Driving experience 15, Vehicle make Toyota, Vehicle model Corolla, Vehicle year 2020, Vehicle value $20,000, and leave Registration number empty, attempt to continue, then assert Quote details remains open and the registration number field shows a field-level error.
