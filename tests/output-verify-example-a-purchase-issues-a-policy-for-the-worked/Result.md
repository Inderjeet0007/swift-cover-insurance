---
test: ../verify-example-a-purchase-issues-a-policy-for-the-worked_test.md
status: passed
started: 2026-09-11T13:28:32.567Z
duration_s: 320
session_id: ce78ab80-53d2-460c-be76-8ce3cdbe257d
---

# Verify Example A purchase issues a policy for the worked premium — Result

## Step 1 ✓ passed (14.6s)
md5: 1cb9a50d629edf6b4287e3ce2cd75f34
Open https://inderjeet0007.github.io/swift-cover-insurance/ in a browser and start the SwiftCover quote-and-buy flow from the Quote details step.

## Step 2 ✓ passed (91.7s)
md5: afbb402f8a113164f8da77b8ed69ed97
On the SwiftCover Quote details step, enter driver age 22, driving experience 2 years, vehicle make Toyota, vehicle model Corolla, vehicle year 2020, vehicle value $15,000, and registration number ABC1234, then continue and assert the Coverage selection step is shown and no policy number matching `SC-` followed by 8 digits is visible on Quote details.

## Step 3 ✓ passed (37.2s)
md5: 92f3d2cfe63618adf5d453b786a2d8b5
On Coverage selection, choose Comprehensive coverage with no add-ons, then assert no policy number matching `SC-` followed by 8 digits is visible on Coverage selection.

## Step 4 ✓ passed (62.6s)
md5: d5ec137b5286d9ad2d9369f676875f1c
Continue to Quote summary, store the displayed premium as summary_premium, and assert the summary premium is $960 and no policy number matching `SC-` followed by 8 digits is visible on Quote summary.

## Step 5 ✓ passed (36.1s)
md5: ca7e486ca7c4bcbe04c9add947599070
Continue to the Payment & confirmation step and assert inputs for card number, expiry, and CVV are shown.

## Step 6 ✓ passed (73.5s)
md5: 18dbb6338d289a9a289195a63ac74865
On the payment step, enter mock card number 4111111111111111, expiry 12/28, and CVV 123, submit the payment, and assert the confirmation screen is shown with a policy number matching `SC-` followed by 8 digits and a final premium paid equal to summary_premium ($960).
