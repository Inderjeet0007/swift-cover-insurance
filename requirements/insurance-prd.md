# Product Requirements Document — Auto Insurance Quote & Buy

**Product:** SwiftCover Auto Insurance — Online Quote & Purchase
**Version:** 1.0
**Status:** Approved for build
**Owner:** Product Team

---

## 1. Overview

SwiftCover lets a customer get an auto insurance quote and purchase a policy
entirely online, in a single guided flow. The customer enters their driver and
vehicle details, selects a coverage tier and optional add-ons, reviews a
calculated premium, pays, and receives a policy number.

This document defines the requirements for the **quote-and-buy flow** only.
Post-purchase features (policy management, renewals, claims) are out of scope for
this version.

## 2. Goals

- Let a customer obtain an accurate quote in under two minutes.
- Calculate premiums transparently from clearly defined rules.
- Complete purchase and issue a policy number in one uninterrupted flow.

## 3. Out of scope

- Policy dashboard, renewals, cancellations, and claims.
- Multi-vehicle or multi-driver policies (one vehicle, one primary driver only).
- Real payment processing (the demo uses a mock payment step).

---

## 4. The flow

The flow has four steps, completed in order:

1. **Quote details** — the customer enters driver and vehicle information.
2. **Coverage selection** — the customer chooses a coverage tier and optional add-ons.
3. **Quote summary** — the system shows the calculated premium and a breakdown.
4. **Payment & confirmation** — the customer pays and receives a policy number.

The customer can move back to a previous step to change inputs; doing so
recalculates the premium.

---

## 5. Detailed requirements

### 5.1 Quote details (Step 1)

The customer must provide:

- **Driver age** (whole number, years)
- **Driving experience** (whole number, years held license)
- **Vehicle make** (text)
- **Vehicle model** (text)
- **Vehicle year** (four-digit year)
- **Vehicle value** (amount in USD)
- **Registration number** (text)

### 5.2 Coverage selection (Step 2)

The customer chooses exactly one **coverage tier**:

- **Third-Party** — covers damage to others only.
- **Comprehensive** — covers the customer's own vehicle plus third-party.

The customer may add any of these optional **add-ons**:

- **Roadside Assistance** — flat $40
- **Zero Depreciation** — flat $75 (Comprehensive only)

### 5.3 Premium calculation (Step 3)

The premium is calculated from a base rate, adjusted by the rules below.

- **Base premium:** $500 for Third-Party, $800 for Comprehensive.
- Add-ons are added to the premium at their flat rates.
- Discounts and surcharges are applied per the acceptance criteria in section 6.

### 5.4 Payment & confirmation (Step 4)

- The customer enters mock payment details (card number, expiry, CVV).
- On successful payment, the system issues a **policy number** in the format
  `SC-` followed by 8 digits (e.g. `SC-10004821`).
- The confirmation screen shows the policy number and the final premium paid.

---

## 6. Acceptance criteria

These are the definitive, testable rules the product must satisfy.

**AC-1 — Young driver surcharge.**
If the driver's age is under 25, a surcharge of 20% is added to the premium
(applied after add-ons, before other discounts).

**AC-2 — Experienced driver discount.**
If the driver has 5 or more years of driving experience, a 10% discount is
applied to the premium.

**AC-3 — Zero Depreciation requires Comprehensive.**
The Zero Depreciation add-on can only be selected when the coverage tier is
Comprehensive. It must not be selectable or applicable with Third-Party cover.

**AC-4 — Vehicle value required for Comprehensive.**
Comprehensive cover requires a vehicle value greater than $0. If the vehicle
value is missing or zero, Comprehensive cannot be selected and the customer is
prompted to enter a valid value.

**AC-5 — Registration number is mandatory and validated.**
The registration number is required. It must be between 4 and 10 alphanumeric
characters. An empty or invalid registration number blocks progress past Step 1
with a clear error message.

**AC-6 — Discount cap.**
The total discount applied to any premium must never exceed 20%, even if
multiple discounts would otherwise combine to more.

**AC-7 — Minimum premium floor.**
The final premium after all discounts must never fall below $300. If
calculations would produce a lower figure, the premium is set to $300.

**AC-8 — Policy number issued only after payment.**
A policy number is generated only after the payment step completes successfully.
No policy number is shown at any earlier step.

---

## 7. Worked examples

These illustrate the acceptance criteria in combination.

**Example A — Young driver, comprehensive, no add-ons**
- Age 22, 2 years experience, vehicle value $15,000, Comprehensive.
- Base $800 → +20% young-driver surcharge (AC-1) = $960.
- No experience discount (under 5 years).
- Final premium: **$960.**

**Example B — Experienced driver, comprehensive, zero-dep add-on**
- Age 40, 15 years experience, vehicle value $20,000, Comprehensive + Zero Dep.
- Base $800 + $75 Zero Dep = $875.
- −10% experience discount (AC-2), capped at 20% (AC-6, not exceeded) = $787.50.
- Above the $300 floor (AC-7).
- Final premium: **$787.50.**

**Example C — Third-party, experienced driver, roadside**
- Age 50, 20 years experience, Third-Party + Roadside.
- Base $500 + $40 Roadside = $540.
- −10% experience discount = $486.
- Final premium: **$486.**

---

## 8. Error and edge handling

- Any required field left empty blocks progress with a field-level error.
- Selecting Zero Depreciation with Third-Party cover is prevented (AC-3).
- Selecting Comprehensive with no vehicle value is prevented (AC-4).
- Invalid registration format is rejected (AC-5).
- The premium shown in the summary must exactly match the amount charged at
  payment.
