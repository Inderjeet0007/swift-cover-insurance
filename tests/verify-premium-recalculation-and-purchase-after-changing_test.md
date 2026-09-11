---
assurance:
  id: t-12
  base: sha256:d709e212c75214d8feac56232ed70e57fc3e6e2305141ffccdcad79d877bd362
---
# Verify premium recalculation and purchase after changing earlier quote inputs

> Prove that when the customer goes back, changes quote-affecting inputs, and returns to payment, the final premium shown and charged reflect the updated quote rather than the earlier amount, and the issued policy is confirmed only after the revised payment succeeds.

## Step 1

Open https://inderjeet0007.github.io/swift-cover-insurance/ in a browser and start the SwiftCover quote-and-buy flow from the Quote details step.

## Step 2 @verifies ac-33

On the SwiftCover Quote details step, enter driver age 22, driving experience 2 years, vehicle make {{vehicle_make}}, vehicle model {{vehicle_model}}, vehicle year {{vehicle_year}}, vehicle value $15,000, and registration number {{registration_number}}, then continue and assert the Coverage selection step is shown and no policy number matching `SC-` followed by 8 digits is visible on Quote details.

## Step 3 @verifies ac-33

On Coverage selection for the initial quote, choose Comprehensive coverage with no add-ons, then assert no policy number matching `SC-` followed by 8 digits is visible on Coverage selection.

## Step 4 @verifies ac-42, ac-33

Continue to Quote summary for the initial quote, store the displayed premium as baseline_premium, and assert the summary premium is $960 and no policy number matching `SC-` followed by 8 digits is visible on Quote summary.

## Step 5

From Quote summary, go back to Quote details, change driver age to 50, driving experience to 20 years, and vehicle value to {{third_party_vehicle_value_usd}}, then return to Coverage selection for the edited quote.

## Step 6 @verifies ac-42, ac-33

On Coverage selection for the edited quote, switch to Third-Party coverage, select Roadside Assistance, continue to Quote summary, store the displayed premium as revised_summary_premium, and assert the summary premium is $486 instead of baseline_premium ($960) and no policy number matching `SC-` followed by 8 digits is visible on Quote summary.

## Step 7 @verifies ac-38, ac-39, ac-40

Continue to the Payment & confirmation step and assert inputs for card number, expiry, and CVV are shown.

## Step 8 @verifies ac-31, ac-32, ac-34, ac-35, ac-36, ac-37

On the payment step, enter mock card number {{card_number}}, expiry {{card_expiry}}, and CVV {{card_cvv}}, submit the payment, and assert the confirmation screen is shown with a policy number matching `SC-` followed by 8 digits and a final premium paid equal to revised_summary_premium ($486).
