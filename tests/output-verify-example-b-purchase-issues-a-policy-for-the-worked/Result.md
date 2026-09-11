---
test: ../verify-example-b-purchase-issues-a-policy-for-the-worked_test.md
status: passed
started: 2026-09-11T13:47:15.721Z
duration_s: 321
session_id: f69d1295-e047-46d5-95ba-d2855275e210
---

# Verify Example B purchase issues a policy for the worked premium — Result

## Step 1 ✓ passed (20.9s)
md5: 1cb9a50d629edf6b4287e3ce2cd75f34
Open https://inderjeet0007.github.io/swift-cover-insurance/ in a browser and start the SwiftCover quote-and-buy flow from the Quote details step.

## Step 2 ✓ passed (85.3s)
md5: da93d94a25a9d68e5179d59774be5962
On the SwiftCover Quote details step, enter driver age 40, driving experience 15 years, vehicle make Toyota, vehicle model Corolla, vehicle year 2020, vehicle value $20,000, and registration number ABC1234, then continue and assert the Coverage selection step is shown and no policy number matching `SC-` followed by 8 digits is visible on Quote details.

## Step 3 ✓ passed (39.4s)
md5: d8bd37bbff64341a4490f6a8d04d9fcd
On Coverage selection, choose Comprehensive coverage and the Zero Depreciation add-on, then assert no policy number matching `SC-` followed by 8 digits is visible on Coverage selection.

## Step 4 ✓ passed (68.5s)
md5: 9c8002370bf4f6c7c8092dc775bd1cdd
Continue to Quote summary, store the displayed premium as summary_premium, and assert the summary premium is $787.50 and no policy number matching `SC-` followed by 8 digits is visible on Quote summary.

## Step 5 ✓ passed (30s)
md5: ca7e486ca7c4bcbe04c9add947599070
Continue to the Payment & confirmation step and assert inputs for card number, expiry, and CVV are shown.

## Step 6 ✓ passed (72.5s)
md5: d44799dde65b61f4aa671b78398b5b3d
On the payment step, enter mock card number 4111111111111111, expiry 12/28, and CVV 123, submit the payment, and assert the confirmation screen is shown with a policy number matching `SC-` followed by 8 digits and a final premium paid equal to summary_premium ($787.50).
