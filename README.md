# ClientBook

A simple iPhone app for keeping a list of clients and the stock each client orders.

- **Clients** – list sorted by customer ID, with search (ID, name or phone) and a delivery-day filter (Mon–Sun). Tap a client to see every stock item they order, add more from your stock list, and add a note per item (e.g. "20 kg weekly").
- **Stock** – list sorted by stock ID (with brand and unit), with search. Tap an item to see which clients order it.
- **Import / Export** – full backup/restore (JSON) and CSV import/export for clients, stock and client orders (opens in Excel / Numbers; Chinese text supported).

Works offline. Data is stored on the phone itself, so export a full backup regularly.

## Put it on your iPhone

1. In this repo on GitHub: **Settings → Pages → Build and deployment → Source: Deploy from a branch**, branch `main`, folder `/ (root)`, **Save**.
2. After a minute the app is live at `https://<your-username>.github.io/clientbook/`.
3. Open that link in **Safari** on the iPhone → tap **Share** → **Add to Home Screen**.

It now opens full-screen from its own icon like a normal app.

## CSV formats

First row must be the headers. Imports add new records and update ones with matching IDs.

| File | Columns |
|---|---|
| Clients | `customer_id, name, phone, delivery_days, notes` — days like `Mon Thu`, `Mon–Sat` or `Daily` |
| Stock | `stock_id, name, brand, unit, notes` |
| Client orders | `customer_id, stock_id, note` (optional: `customer_name, stock_name, unit, added`) |

When importing orders, any client or stock ID not already in the app is created automatically.

## Files

- `index.html` – the whole app (HTML, CSS, JavaScript; no build step)
- `sw.js` – offline support
- `manifest.webmanifest`, `icons/` – home-screen app details
