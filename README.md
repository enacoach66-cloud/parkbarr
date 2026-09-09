# Park Bar & Club Manager

A local-first digital replacement for the club/bar's paper stock and sales ledgers.

## Run

```bash
npm install
npm start
```

Open http://localhost:3000

## Vercel deployment

Set **Root Directory** to `club_system` when importing this repository. The
included `vercel.json` routes the site and API through the Express server.

The application uses the configured PostgreSQL database as its only persistent
store. For Vercel, set `DATABASE_URL` to Supabase's **Transaction pooler**
connection string (port `6543`), not the Session pooler string (port `5432`).
The server intentionally limits each function instance to one database client;
this prevents a burst of serverless instances from exhausting Supabase's
session-pool connection limit.

There is no default account. An authorized administrator creates accounts through
the user-management screen. Store connection details only in deployment
environment variables; never commit `.env` files.

## Included
- Products and categories imported from the photographed paper stock sheets.
- Buying/selling prices, estimated-price flags and price history.
- Sales with automatic stock deduction.
- Purchases/suppliers/invoices with automatic stock increase.
- Stock movements and low-stock/reorder alerts.
- Product intelligence: current buy/sell price, margin, units sold this week, 7-day sales trend, current stock and reorder recommendation.
- Expenses.
- Daily cash closing and cash variance.
- Daily/weekly/monthly reports, stock valuation, COGS/gross profit and net result.
- A4 printing and CSV export.
- Roles, audit trail and database backup.

## Important
The product catalog was transcribed from photographed handwritten/printed stock sheets. Where a price was not clear enough to read confidently, the application uses an estimated value and displays `ESTIMATED`. Replace those values with the club's confirmed prices before relying on them for accounting.
