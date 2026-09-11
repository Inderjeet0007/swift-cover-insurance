---
test: ../verify-premium-recalculation-and-purchase-after-changing_test.md
status: passed
started: 2026-09-11T15:27:02.268Z
duration_s: 456
session_id: 9fb8e9a9-3c72-483d-9d46-d19cde34e07a
---

# Verify premium recalculation and purchase after changing earlier quote inputs — Result

## Step 1 ✓ passed (16.6s)
md5: 1cb9a50d629edf6b4287e3ce2cd75f34
Open https://inderjeet0007.github.io/swift-cover-insurance/ in a browser and start the SwiftCover quote-and-buy flow from the Quote details step.

## Step 2 ✓ passed (77.2s)
md5: b3c933107d807c671e369379ebf3a792
On the SwiftCover Quote details step, enter driver age 22, driving experience 2 years, vehicle make Toyota, vehicle model Camery, vehicle year 2019, vehicle value $15,000, and registration number TY938A, then continue and assert the Coverage selection step is shown and no policy number matching `SC-` followed by 8 digits is visible on Quote details.

## Step 3 ✓ passed (41s)
md5: 32d7883107998d8262adefcc718c7216
On Coverage selection for the initial quote, choose Comprehensive coverage with no add-ons, then assert no policy number matching `SC-` followed by 8 digits is visible on Coverage selection.

## Step 4 ✓ passed (42.3s)
md5: 0d1cf387d0d5221f5ac03cbce203ce24
Continue to Your Quote section for the initial quote, store the total premium as baseline_premium, and assert the Total Premium is $960 and no policy number matching `SC-` followed by 8 digits is visible on Quote summary.

## Step 5 ✓ passed (78.1s)
md5: 4b991a5f12ac2dbc96164af1b7f542a3
From Your Quote section, go back to the Details section, change driver age to 50, driving experience to 20 years, and vehicle value to $26000, then return to Coverage selection for the edited quote.

## Step 6 ✓ passed (97s)
md5: 8753feb2efae615d4d452a105ebf27e5
On Coverage selection for the edited quote, switch to Third-Party coverage, select Roadside Assistance, continue to Quote summary, store the displayed premium as revised_summary_premium, and assert the summary premium is $486 instead of baseline_premium ($960) and no policy number matching `SC-` followed by 8 digits is visible on Quote summary.

## Step 7 ✓ passed (29.7s)
md5: ca7e486ca7c4bcbe04c9add947599070
Continue to the Payment & confirmation step and assert inputs for card number, expiry, and CVV are shown.

## Step 8 ✓ passed (68.3s)
md5: 5a47c1911b0964a129529c0813c94413
On the payment step, enter mock card number 4111111111111111, expiry 12/28, and CVV 123, submit the payment, and assert the confirmation screen is shown with a policy number matching `SC-` followed by 8 digits and a final premium paid equal to revised_summary_premium ($486).
