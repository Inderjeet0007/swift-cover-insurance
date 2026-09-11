---
assurance:
  id: t-2
  base: sha256:134184e497b1246a45a87ae4e565b3ae03ea9f8250db61866e499744a14769dd
---
# Verify Example A premium for a young driver with Comprehensive coverage

> Prove the quote summary applies the Comprehensive base premium and the under-25 surcharge to produce the worked-example premium of $960 without an experience discount.

## Step 1

Open https://inderjeet0007.github.io/swift-cover-insurance/ in a browser and start a new SwiftCover auto insurance quote from the Quote details step.

## Step 2

On Quote details, enter Driver age 22, Driving experience 2, Vehicle make Toyota, Vehicle model Corolla, Vehicle year 2020, Vehicle value $15,000, and Registration number ABC1234, then continue to Coverage selection.

## Step 3 @verifies ac-10

On Coverage selection, choose Comprehensive as the coverage tier with no add-ons selected, then assert Comprehensive is the only selected coverage tier.

## Step 4 @verifies ac-25, ac-1, ac-3, ac-6, ac-14, ac-15

Continue to Quote summary, then assert the summary shows a calculated premium of $960 and a premium breakdown that includes Comprehensive base premium $800 and a 20% young-driver surcharge.
