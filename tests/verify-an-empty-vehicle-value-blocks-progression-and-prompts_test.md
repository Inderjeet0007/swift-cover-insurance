---
assurance:
  id: t-6
  base: sha256:6702d60a5a504277d548f3897c01a110e7e21dff4e99a6d2c28d39e5aa616cc2
---
# Verify an empty vehicle value blocks progression and prompts for a valid value

> Prove Comprehensive cannot be selected when vehicle value is missing and that the customer is prompted to enter a valid value.

## Step 1

Open https://inderjeet0007.github.io/swift-cover-insurance/ in a browser and start a new SwiftCover auto insurance quote from the Quote details step.

## Step 2 @verifies ac-12, ac-13

On Quote details, enter Driver age 40, Driving experience 15, Vehicle make Toyota, Vehicle model Corolla, Vehicle year 2020, leave Vehicle value empty, enter Registration number ABC1234, attempt to continue toward Coverage selection, then assert Quote details remains open, Coverage selection does not open, and a prompt to enter a valid vehicle value is shown.
