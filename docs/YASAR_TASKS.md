# Yasar Tasks

Role: Payment support owner  
Primary ownership: payment audit, donation reliability review, receipt review, audit log review, and launch readiness support. Mikhail owns the final payment implementation decisions.

## Setup Checklist

- [ ] Read `README.md`.
- [ ] Read `docs/CODEBASE_MAP.md`.
- [ ] Pull the latest `main` branch before starting work.
- [ ] Create a feature branch using `feature/<short-description>` or `fix/<short-description>`.
- [ ] Confirm local environment variables are configured for Convex, Clerk, and Flutterwave sandbox.
- [ ] Confirm you can run `bun run build`.

## Week 1: Payment Audit and Flow Support

- [ ] Review `convex/paymentCheckout.ts`.
- [ ] Review `convex/paymentWebhook.ts`.
- [ ] Review `convex/paymentEvents.ts`.
- [ ] Review `convex/donations.ts`.
- [ ] Review `convex/receipts.ts`.
- [ ] Review `convex/receiptDispatch.ts`.
- [ ] Review `src/app/api/donations/checkout/` if present or create a task note if it is missing.
- [ ] Document the current checkout flow from donate button to completed receipt.
- [ ] Give Mikhail notes on missing or risky payment states.
- [ ] Confirm with Mikhail which Flutterwave sandbox settings need final approval.
- [ ] List every possible payment state for Mikhail to approve: pending, paid, failed, cancelled, expired, duplicate webhook, invalid webhook.
- [ ] Open a PR with payment audit notes or implementation changes.

## Week 2: Checkout Review Support

- [ ] Review Mikhail's donation intent implementation.
- [ ] Review that donation amount validation happens on the server.
- [ ] Review that currency validation happens on the server.
- [ ] Review that campaign and fund IDs are validated on the server.
- [ ] Review that the client cannot choose or alter trusted payment status.
- [ ] Review that checkout creates a donation intent before redirecting to Flutterwave.
- [ ] Review failed payment user-facing status.
- [ ] Review cancelled payment user-facing status.
- [ ] Review that expired intents cannot be completed.
- [ ] Add or update tests where practical for donation intent rules.
- [ ] Open a PR only for support fixes assigned by Mikhail.

## Week 3: Webhook, Receipt, and Audit Review

- [ ] Review Flutterwave webhook signature verification.
- [ ] Review invalid webhook rejection.
- [ ] Review duplicate webhook handling.
- [ ] Review amount validation against the original donation intent.
- [ ] Review currency validation against the original donation intent.
- [ ] Review unknown payment reference handling.
- [ ] Review payment event traceability.
- [ ] Review completed donation creation.
- [ ] Review receipt queueing or creation.
- [ ] Review receipt retry behavior.
- [ ] Review audit logs for payment-critical state changes.
- [ ] Open a PR only for support fixes assigned by Mikhail.

## Week 4: Production Launch Readiness

- [ ] Help Mikhail confirm Flutterwave production settings are documented but not enabled before sandbox sign-off.
- [ ] Help Mikhail confirm production webhook URL is configured correctly.
- [ ] Help Mikhail confirm production redirect URLs are configured correctly.
- [ ] Confirm no payment secrets are committed.
- [ ] Confirm sandbox donation works from start to receipt.
- [ ] Confirm duplicate webhook test does not duplicate a donation.
- [ ] Confirm invalid webhook signature is rejected.
- [ ] Confirm failed and cancelled payments produce clear user states.
- [ ] Write support payment launch notes for Mikhail.
- [ ] Help review intern donation-related PRs.

## PR Checklist

- [ ] PR explains what changed.
- [ ] PR explains why it changed.
- [ ] PR explains how to test it.
- [ ] `bun run build` passes.
- [ ] Payment-sensitive support changes have clear manual verification notes.
- [ ] Mikhail is requested as final reviewer.
