---
assurance:
  id: t-5
  base: sha256:f307da271e8556944ee0e266241962bf776ec57460937193fa77f836ca2cbbdf
---
# Verify Third-Party coverage prevents Zero Depreciation selection

> Prove Zero Depreciation cannot be selected when the coverage tier is Third-Party.

## Step 1

Open https://inderjeet0007.github.io/swift-cover-insurance/ in a browser and start a new SwiftCover auto insurance quote from the Quote details step.

## Step 2

On Quote details, enter Driver age 40, Driving experience 15, Vehicle make Toyota, Vehicle model Corolla, Vehicle year 2020, Vehicle value $20,000, and Registration number ABC1234, then continue to Coverage selection.

## Step 3 @verifies ac-10, ac-11

On Coverage selection, choose Third-Party as the coverage tier and try to choose Zero Depreciation, then assert Third-Party remains the only selected coverage tier and Zero Depreciation is not selectable.
