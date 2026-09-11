---
assurance:
  id: t-3
  base: sha256:ae8e9ca832ae3f9ce12d523b1952f41ecf1a958611a976f90f202e2ac66fcebe
---
# Verify premium recalculation after changing an earlier quote input

> Prove that going back to a previous step, changing a quote-affecting input, and returning to Quote summary updates the premium from the new inputs.

## Step 1

Open https://inderjeet0007.github.io/swift-cover-insurance/ in a browser and start a new SwiftCover auto insurance quote from the Quote details step.

## Step 2

On Quote details, enter Driver age 22, Driving experience 2, Vehicle make Toyota, Vehicle model Corolla, Vehicle year 2020, Vehicle value $15,000, and Registration number ABC1234, then continue to Coverage selection.

## Step 3 @verifies ac-1, ac-3, ac-6, ac-10, ac-14, ac-15

On Coverage selection, choose Comprehensive as the coverage tier with no add-ons selected, continue to Quote summary, store the shown premium as baseline_premium, then assert the summary shows a calculated premium of $960, a premium breakdown that includes Comprehensive base premium $800 and a 20% young-driver surcharge, and Comprehensive as the only selected coverage tier.

## Step 4 @verifies ac-1, ac-14, ac-15, ac-23, ac-26

From Quote summary, return to Quote details, change Driver age from 22 to 25 while keeping Driving experience 2, Vehicle make Toyota, Vehicle model Corolla, Vehicle year 2020, Vehicle value $15,000, and Registration number ABC1234 unchanged, return to Quote summary, then assert the recalculated premium is $800, differs from baseline_premium, and the breakdown no longer shows a young-driver surcharge.
