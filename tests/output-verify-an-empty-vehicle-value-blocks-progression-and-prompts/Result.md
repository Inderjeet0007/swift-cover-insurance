---
test: ../verify-an-empty-vehicle-value-blocks-progression-and-prompts_test.md
status: passed
started: 2026-09-11T12:49:18.879Z
duration_s: 136
session_id: 3f8546ee-9906-4ea4-aa14-61cdcbf91582
---

# Verify an empty vehicle value blocks progression and prompts for a valid value — Result

## Step 1 ✓ passed (23.8s)
md5: 6deed9cf5dee64085c3cb37e31ec5d8d
Open https://inderjeet0007.github.io/swift-cover-insurance/ in a browser and start a new SwiftCover auto insurance quote from the Quote details step.

## Step 2 ✓ passed (108.3s)
md5: d9586289080fd98ce30ced6f4b028336
On Quote details, enter Driver age 40, Driving experience 15, Vehicle make Toyota, Vehicle model Corolla, Vehicle year 2020, leave Vehicle value empty, enter Registration number ABC1234, attempt to continue toward Coverage selection, then assert Quote details remains open, Coverage selection does not open, and a prompt to enter a valid vehicle value is shown.
