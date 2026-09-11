---
test: ../verify-example-c-purchase-issues-a-policy-for-the-worked_test.md
status: passed
started: 2026-09-11T14:06:40.416Z
duration_s: 420
session_id: 5f73267b-fdc4-42d3-8ed4-69eb6ee43b98
---

# Verify Example C purchase issues a policy for the worked premium — Result

## Step 1 ✓ passed (24.3s)
md5: 1cb9a50d629edf6b4287e3ce2cd75f34
Open https://inderjeet0007.github.io/swift-cover-insurance/ in a browser and start the SwiftCover quote-and-buy flow from the Quote details step.

## Step 2 ✓ passed (101.1s)
md5: 068c5357f914013c53f805563dc98419
On the SwiftCover Quote details step, enter driver age 50, driving experience 20 years, vehicle make Toyota, vehicle model Corolla, vehicle year 2021, vehicle value $35,000, and registration number A87D, then continue and assert the Coverage selection step is shown and no policy number matching `SC-` followed by 8 digits is visible on Quote details.

## Step 3 ✓ passed (49.4s)
md5: 812c6bcb2857a5ede5c24923fbef9438
On Coverage selection, choose Third-Party coverage and the Roadside Assistance add-on, then assert no policy number matching `SC-` followed by 8 digits is visible on Coverage selection.

## Step 4 ✓ passed (69.5s)
md5: 9c6c793f7dc42c672e809760473d003a
Continue to Quote summary, store the displayed premium as summary_premium, and assert the summary premium is $486 and no policy number matching `SC-` followed by 8 digits is visible on Quote summary.

## Step 5 ✓ passed (40.1s)
md5: ca7e486ca7c4bcbe04c9add947599070
Continue to the Payment & confirmation step and assert inputs for card number, expiry, and CVV are shown.

## Step 6 ✓ passed (131.3s)
md5: f5fe931e88d7856aa78ad47b9e6bd15a
On the payment step, enter mock card number 4111111111111111, expiry 12/28, and CVV 123, submit the payment, and assert the confirmation screen is shown with a policy number matching `SC-` followed by 8 digits and a final premium paid equal to summary_premium ($486).
