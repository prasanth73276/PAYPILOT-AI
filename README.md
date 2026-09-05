# PAYPILOT AI — Agentic Commerce Growth Platform

PAYPILOT AI is a demo platform where an AI growth agent analyzes customer intent, generates a bounded personalized offer, requests merchant approval, creates a Razorpay Test Mode order only after approval, handles payment outcomes, and records an audit trail.

## Demo flow
1. Enter a customer message.
2. AI analyzes intent and recommends an offer.
3. Merchant reviews the explanation and approves/rejects the offer.
4. Only an approved offer can create a Razorpay order.
5. Razorpay Test Mode Checkout opens.
6. Success/failure is recorded.
7. A failure triggers an AI recovery recommendation.
8. The audit trail shows every important AI and payment action.

## Run locally

```bash
npm install
cp .env.example .env
# Put Razorpay Test Mode keys in .env
npm start
```

Open http://localhost:3000

## Security / bounded money actions
- AI never creates a payment order directly.
- A merchant approval record is required.
- Offer discounts are capped server-side at 15%.
- Payment amount is calculated server-side from the approved offer.
- Razorpay keys are read from environment variables; `.env` is ignored by Git.
- Successful Razorpay payments are signature-verified server-side.
- AI and payment actions are recorded in the audit trail.

## Tech
Node.js + Express + Razorpay Test Mode + HTML/CSS/JavaScript.