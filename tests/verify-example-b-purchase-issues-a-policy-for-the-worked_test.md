---
assurance:
  id: t-13
  base: sha256:fea50d04d6392f26b60b53b56c615ef928acb96d4ef6332e1caac67f7cc85cbd
---
# Verify Example B purchase issues a policy for the worked premium

> Prove that a customer can complete payment for the Example B quote and receive confirmation showing policy issuance and the exact final premium of $787.50.

## Step 1

Open https://inderjeet0007.github.io/swift-cover-insurance/ in a browser and start the SwiftCover quote-and-buy flow from the Quote details step.

## Step 2 @verifies ac-33

On the SwiftCover Quote details step, enter driver age 40, driving experience 15 years, vehicle make Toyota, vehicle model Corolla, vehicle year 2020, vehicle value $20,000, and registration number ABC1234, then continue and assert the Coverage selection step is shown and no policy number matching `SC-` followed by 8 digits is visible on Quote details.

## Step 3 @verifies ac-33

On Coverage selection, choose Comprehensive coverage and the Zero Depreciation add-on, then assert no policy number matching `SC-` followed by 8 digits is visible on Coverage selection.

## Step 4 @verifies ac-43, ac-33

Continue to Quote summary, store the displayed premium as summary_premium, and assert the summary premium is $787.50 and no policy number matching `SC-` followed by 8 digits is visible on Quote summary.

## Step 5 @verifies ac-38, ac-39, ac-40

Continue to the Payment & confirmation step and assert inputs for card number, expiry, and CVV are shown.

## Step 6 @verifies ac-31, ac-32, ac-34, ac-35, ac-36, ac-37

On the payment step, enter mock card number 4111111111111111, expiry 12/28, and CVV 123, submit the payment, and assert the confirmation screen is shown with a policy number matching `SC-` followed by 8 digits and a final premium paid equal to summary_premium ($787.50).
