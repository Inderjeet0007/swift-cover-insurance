---
assurance:
  id: t-1
  base: sha256:12d8ba3826ce768e216de0341cbf800c8f3fa6a6b74b517251022005ef99e59e
---
# Verify Example B premium for Comprehensive coverage with Zero Depreciation

> Prove the quote summary applies the Comprehensive base premium, the Zero Dep add-on, and the 10% experience discount to produce the worked-example premium of $787.50.

## Step 1

Open https://inderjeet0007.github.io/swift-cover-insurance/ in a browser and start a new SwiftCover auto insurance quote from the Quote details step.

## Step 2

On Quote details, enter Driver age 40, Driving experience 15, Vehicle make Toyota, Vehicle model Corolla, Vehicle year 2020, Vehicle value $20,000, and Registration number ABC1234, then continue to Coverage selection.

## Step 3 @verifies ac-10

On Coverage selection, choose Comprehensive as the coverage tier, select Zero Depreciation, leave Roadside Assistance unselected, then assert Comprehensive is the only selected coverage tier.

## Step 4 @verifies ac-24, ac-1, ac-3, ac-5, ac-7, ac-8, ac-14, ac-15

Continue to Quote summary, then assert the summary shows a calculated premium of $787.50 and a premium breakdown that includes Comprehensive base premium $800, Zero Depreciation $75, and a 10% driving-experience discount.
