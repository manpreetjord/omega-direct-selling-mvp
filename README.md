# Omega+ Direct-Selling MVP

Runnable local MVP for the agreed concept: ₹1,000 product price, admin-issued single-use PINs, and a one-child-per-member linear chain of unlimited depth.

## Run
Requires Node.js 20+.
```bash
cp .env.example .env
# Change SESSION_SECRET and ADMIN_PASSWORD
npm install
npm start
```
Open http://localhost:3000. Admin credentials are configured in `.env`.

## Included
- Responsive storefront and demo order request form
- Member registration with a one-time admin-issued PIN
- bcrypt password hashing and role-protected admin endpoints
- Admin PIN creation, member list, order list and summary
- Member chain position, direct child and upline
- SQLite persistence and basic audit events
- Database uniqueness on `network.parent_id` enforces at most one direct child

For a single global line, issue the next PIN assigned to the current tail member. Root PINs have no parent.

## Not live / production-ready
Payments are not collected. Commission computation, wallet credit and payouts are intentionally disabled. The order route is a request-only demo. Add verified Razorpay webhook handling, idempotency, refunds, invoice/tax logic and fulfilment before live sales. Replace SQLite with PostgreSQL, Express in-memory sessions with a managed store, add CSRF protection, MFA, OTP/email verification, KYC, backups, monitoring and automated security tests.

Before launch, confirm entity and seller agreements, direct-selling compensation plan, GST treatment, product manufacturing/fulfilment economics, FSSAI licence, approved label and permitted claims. A free PIN must not become an entry fee or a route to recruitment rewards. Commission eligibility must be tied to bona fide product sales under a legally reviewed plan. An unlimited member chain does not imply unlimited commission levels.

## Commission assumption awaiting approval
Working assumption: qualifying sales are credited to the member who generated them; eligible upstream members may receive commission under a finite or capped, legally reviewed schedule. No commissions are calculated or paid in this starter.
