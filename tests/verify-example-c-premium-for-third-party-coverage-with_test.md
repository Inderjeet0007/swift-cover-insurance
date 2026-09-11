---
assurance:
  id: t-4
  base: sha256:942e5a0f55a93093cc792d92f84437c18d4a9f5fdd05d1fbde11404478559847
---
# Verify Example C premium for Third-Party coverage with Roadside Assistance

> Prove the quote summary applies the Third-Party base premium, the Roadside add-on, and the 10% experience discount to produce the worked-example premium of $486.

## Step 1

Open https://inderjeet0007.github.io/swift-cover-insurance/ in a browser and start a new SwiftCover auto insurance quote from the Quote details step.

## Step 2

On Quote details, enter Driver age 50, Driving experience 20, Vehicle make Toyota, Vehicle model Corolla, Vehicle year 2020, Vehicle value $15,000, and Registration number ABC1234, then continue to Coverage selection.

## Step 3 @verifies ac-10

On Coverage selection, choose Third-Party as the coverage tier, select Roadside Assistance, leave Zero Depreciation unselected, then assert Third-Party is the only selected coverage tier.

## Step 4 @verifies ac-27, ac-1, ac-2, ac-4, ac-7, ac-8, ac-14, ac-15

Continue to Quote summary, then assert the summary shows a calculated premium of $486 and a premium breakdown that includes Third-Party base premium $500, Roadside Assistance $40, and a 10% driving-experience discount.
