
# ORIBA MARKET — ORIBA HOLDING

Starter application for a multi-vendor marketplace. Includes a responsive React + TypeScript storefront, Express API, PostgreSQL/Prisma schema, and setup instructions.

## Important status
This is a runnable **development MVP foundation**, not a certified production payment platform. Payment providers, SMS/email delivery, legal company verification, hosting, backups, and production security review require real credentials and operator approval. No payment is falsely marked as paid.

## Requirements
- Node.js 20+
- npm 10+
- PostgreSQL 15+

## 1. Start the API
```bash
cd server
cp .env.example .env
# Edit DATABASE_URL for your PostgreSQL database
npm install
npx prisma generate
npx prisma migrate dev --name init
npm run dev
```
API runs at http://localhost:4000. Health check: http://localhost:4000/api/health

## 2. Start the web app
Open another terminal:
```bash
cd client
npm install
npm run dev
```
Open the URL printed by Vite (normally http://localhost:5173).

## Included features
- Responsive marketplace home page
- Product catalogue, category filtering and text search
- Product detail modal and shopping cart
- Demo checkout that creates an order request (not a payment)
- API product endpoint and order-request endpoint
- PostgreSQL schema for users, sellers, products, orders and order items
- Server-side request validation and basic security middleware

## Before real public launch
1. Replace demo product data with approved database-backed catalogue data.
2. Add production authentication (verified email/phone, secure sessions, MFA for admins).
3. Implement seller onboarding and document review by authorized staff.
4. Integrate payment providers only after contracts, credentials and sandbox/live testing.
5. Add shipping provider integrations, tax/legal rules, customer support and dispute handling.
6. Configure HTTPS, secure secrets, rate limits, monitoring, backups and disaster recovery.
7. Run dependency, penetration, accessibility and load tests.
8. Obtain legal review for privacy, consumer protection and marketplace terms in each country.

## Project structure
```text
ORIBA_MARKET/
  client/       React + TypeScript storefront
  server/       Express API + Prisma + PostgreSQL schema
  docs/         architecture and launch checklist
```
