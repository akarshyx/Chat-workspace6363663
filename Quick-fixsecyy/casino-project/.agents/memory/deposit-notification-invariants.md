---
name: Deposit notification invariants
description: Rules for keeping crypto deposit settlement, fees, notifications, and explorer links consistent.
---

The settlement layer must pass the gross provider USD value to the confirmation renderer; the renderer derives the fee-adjusted credited value from the separate fee field.

**Why:** Passing the net amount as gross causes the fee to be subtracted twice in the user-facing confirmation while accounting totals remain correct.

**How to apply:** Keep gross USD, credited USD, fee USD, coin amount, network, and txid as separate values across provider verification, balance crediting, and notification retry payloads.