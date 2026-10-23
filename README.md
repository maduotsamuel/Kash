# JAMB TRADE MVP

A mobile-friendly B2B wholesale marketplace prototype for Juba, South Sudan. Built with Vite, Bootstrap, vanilla JavaScript, Supabase Auth and PostgreSQL.

## Run locally

1. Install Node.js 20 or later.
2. Run `npm install`.
3. Copy `.env.example` to `.env` and enter your Supabase project URL and **publishable/anon** key (never the service-role key).
4. In Supabase SQL Editor, run `supabase/migrations/001_initial.sql`.
5. Run `npm run dev` and open the displayed address.

Without environment credentials, the app runs in **clearly labelled demo mode**. Demo products are fictional. Checkout and authentication are unavailable in demo mode.

## First-use workflow

1. Sign up and confirm your email if required by Supabase Auth settings.
2. Sign in and register a retailer or wholesaler business.
3. An administrator must verify a wholesaler and add products through the Supabase dashboard or controlled admin tooling before their listings become visible.
4. Retailers can place orders with **one supplier per order**. Suppliers can confirm orders through the Orders view.
5. Payment and delivery execution are **not implemented** in this MVP. Do not use it to collect real payments or promise fulfilment until those workflows are built and tested.

## Security

- RLS protects tenant data and catalogue exposure.
- Checkout and supplier confirmation are SECURITY DEFINER PostgreSQL functions with explicit authorization checks and locked stock rows.
- Do not publish a Supabase service-role key in frontend environment variables.
- No admin account is seeded. Admins are provisioned manually through secure database administration.

## Next development phases

- Verified wholesaler onboarding and secure admin dashboard
- Supplier product management and inventory movements
- Delivery dispatch, driver accounts, proof of delivery and exception workflows
- Verified payment records, supplier settlements, refunds and commission reporting
- Tests for concurrency, access controls, order transitions and network failures

This is a working **phase-one foundation**, not a production-ready marketplace. Run security and operational tests before accepting real transactions.
