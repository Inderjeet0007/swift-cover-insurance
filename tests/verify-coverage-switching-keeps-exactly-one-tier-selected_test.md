---
assurance:
  id: t-11
  base: sha256:1cf41783d9f7607c18beb3363b1a3ca8515c6d5fb25bd13f360b90b6aa81c2dc
---
# Verify coverage switching keeps exactly one tier selected

> Prove the customer can hold exactly one selected coverage tier across Third-Party and Comprehensive choices.

## Step 1

Open https://inderjeet0007.github.io/swift-cover-insurance/ in a browser and start a new SwiftCover auto insurance quote from the Quote details step.

## Step 2

On Quote details, enter Driver age 40, Driving experience 15, Vehicle make Toyota, Vehicle model Corolla, Vehicle year 2020, Vehicle value $20,000, and Registration number ABC1234, then continue to Coverage selection.

## Step 3 @verifies ac-10, ac-30

On Coverage selection, choose Third-Party, switch the selection to Comprehensive, then assert Comprehensive is selected, Third-Party is no longer selected, and exactly one coverage tier is selected.
