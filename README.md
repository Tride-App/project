## Tride — Intercity Carpooling on Stellar

### Introduction

Tride is a non-custodial, escrow-based intercity carpooling marketplace built on Stellar, enabling drivers to monetize empty seats and passengers to book verified rides with transparent payments and enforceable cancellation rules.

---

## The problem

Intercity travel often suffers from:

- high costs and unreliable pricing,
- lack of trust between strangers,
- cancellations/no-shows with no fair recourse,
- fragmented payment experiences (cash, transfers, scams, disputes).

Drivers regularly travel with empty seats, while passengers struggle to find safe, affordable, predictable options—especially for common routes (e.g., Kaduna → Abuja).

---

## The solution

Tride connects drivers and passengers for **seat-based bookings** on scheduled intercity trips. The key innovation is **mandatory on-chain escrow** that enforces clear rules for:

- booking and seat inventory,
- cancellations and refunds,
- driver payouts and platform fees,
- no-show handling,
- automatic payout finalization (no admin / no discretionary control).

All trip logistics (pickup point, identity verification, chat, navigation) remain off-chain for privacy and usability, while **payments and settlement are on-chain** for transparency and reliability.

---

## How it works (user flow)

1. A driver posts a trip (Origin → Destination, departure time, price per seat, available seats).
2. Passengers discover trips and book **1+ seats** (group bookings supported).
3. Passenger funds are locked in **USDC escrow on Stellar** (non-custodial).
4. At pickup, the passenger confirms they’ve boarded (passenger-signed check-in).
5. On completion:
   - both can confirm completion, **or**
   - the driver can auto-finalize payout after an arrival timeout (prevents griefing).
6. The driver is paid, and the platform takes a percentage fee.

---

## Why Stellar + USDC

- **Fast, low-fee settlement** suited for frequent small transactions.
- **USDC pricing** keeps fares stable and understandable.
- Strong ecosystem support for payments-focused consumer apps.
- Smart contracts (Soroban) enable programmable escrow without custody.

---

## Trust & safety design (pragmatic, v1-ready)

Tride separates concerns:

- **On-chain:** escrow, refunds, payouts, platform fee, immutable settlement receipts.
- **Off-chain:** identity verification, driver/vehicle profiles, ratings, messaging, dispute evidence, and route logistics.

To reduce abuse without an admin key:

- Passenger check-in (“boarded”) is a **passenger-signed on-chain action**.
- No-show rules have a **grace window** and are enforced by contract logic.
- Reputation/verification can be layered in over time.

---

## Cancellation & refund policy (clear + enforceable, no-admin)

Tride uses time-based rules around the scheduled departure:

- Early cancellation → full refund
- Later cancellation → partial refund + driver compensation + small platform fee
- No-show → driver compensated
- Driver cancels → full refund to passengers
- After “boarded,” driver can still receive payout via **timeout auto-finalize**, even if passenger disappears

This makes outcomes predictable and reduces disputes.

---

## Business model

- **Take rate** on completed rides (e.g., 10%).
- Smaller fee on late cancellations/no-shows (e.g., 5%).
- Future optional revenue: verification services, premium placement for drivers, subscription tiers for frequent drivers, route-based partnerships.

---

## What makes Tride different

- **Non-custodial escrow by default** (users control their funds; no platform custody risk).
- **Deterministic settlement rules** (no admin arbitration required).
- **Seat inventory & group bookings** built into the payment layer.
- Designed for **real intercity commerce**, not just crypto payments.

---

## MVP scope (what we plan to ship first)

**Web app + smart contracts** for one initial corridor (e.g., Kaduna ↔ Abuja):

- Driver trip creation (price per seat, schedule, capacity)
- Passenger discovery + booking (multi-seat)
- USDC escrow funding
- Boarding confirmation
- Completion + auto-finalize payout
- Cancellation/no-show flows
- Basic off-chain profiles + ratings hooks

---

## What we’re looking for

### Partners / investors

- Strategic support to expand route coverage, onboard drivers, and build trust/verification rails.
- Stellar ecosystem partners for tooling, grants, and stablecoin/payment integrations.

### Contributing

We welcome contributors across:

- Soroban smart contract engineering (escrow + state machine)
- Frontend (React/Next.js) + Stellar wallet integrations
- Indexing/event processing (to power trip search + booking status)
- Off-chain/API design (for profiles, ratings, messaging)
- Security reviews (contract + app)
- Product design and UX (boarding flow, safety UX, verification UX)

---
