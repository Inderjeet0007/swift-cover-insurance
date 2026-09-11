---
assurance:
  id: t-7
  base: sha256:9619a9898d9423bee5da22f5cd9cce473137190b638bf923c4edb3da8e144dda
---
# Verify a zero vehicle value prevents Comprehensive selection

> Prove Comprehensive cannot be selected when vehicle value is 0 and that the customer is prompted to enter a valid value.

## Step 1

Open https://inderjeet0007.github.io/swift-cover-insurance/ in a browser and start a new SwiftCover auto insurance quote from the Quote details step.

## Step 2

On Quote details, enter Driver age 40, Driving experience 15, Vehicle make Toyota, Vehicle model Corolla, Vehicle year 2020, Vehicle value $0, and Registration number ABC1234, then continue to Coverage selection.

## Step 3 @verifies ac-12, ac-13

On the Coverage selection, verify that the Comprehensive coverage option is disabled (not selectable) and that the hint "Enter a vehicle value greater than $0" is displayed. Confirm Third-Party remains selectable. This completes the scenario.
