---
assurance:
  id: t-14
  base: sha256:0b6ba87e1c190b9ed14dfba4b84ab0d3f4aa08092ab41bf0dcff284650f8d257
---
# Verify Example A purchase issues a policy for the worked premium

> Prove that a customer can complete payment for the Example A quote and receive confirmation showing policy issuance and the exact final premium of $960.

## Step 1

Open https://inderjeet0007.github.io/swift-cover-insurance/ in a browser and start the SwiftCover quote-and-buy flow from the Quote details step.

## Step 2 @verifies ac-33

On the SwiftCover Quote details step, enter driver age 22, driving experience 2 years, vehicle make Toyota, vehicle model Corolla, vehicle year 2020, vehicle value $15,000, and registration number ABC1234, then continue and assert the Coverage selection step is shown and no policy number matching `SC-` followed by 8 digits is visible on Quote details.

## Step 3 @verifies ac-33

On Coverage selection, choose Comprehensive coverage with no add-ons, then assert no policy number matching `SC-` followed by 8 digits is visible on Coverage selection.

## Step 4 @verifies ac-44, ac-33

Continue to Quote summary, store the displayed premium as summary_premium, and assert the summary premium is $960 and no policy number matching `SC-` followed by 8 digits is visible on Quote summary.

## Step 5 @verifies ac-38, ac-39, ac-40

Continue to the Payment & confirmation step and assert inputs for card number, expiry, and CVV are shown.

## Step 6 @verifies ac-31, ac-32, ac-34, ac-35, ac-36, ac-37

On the payment step, enter mock card number 4111111111111111, expiry 12/28, and CVV 123, submit the payment, and assert the confirmation screen is shown with a policy number matching `SC-` followed by 8 digits and a final premium paid equal to summary_premium ($960).
