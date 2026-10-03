# Invoice Manager

**Offline-first invoice, quotation, and notes app** — single HTML file, no server required.

Manage invoices, quotations, credit/debit notes, customers, and products in the browser. Data stays on your device (localStorage). Optional Google Sheets sync.

---

## Suggested GitHub setup

| Field | Value |
|--------|--------|
| **Repository name** | `invoice-manager` |
| **Description** | Offline-first invoice & quotation manager — PDF export, WhatsApp Web, custom columns, multi-company. Single HTML file. |
| **Visibility** | Public or Private |
| **Topics** | `invoice`, `quotation`, `pdf`, `offline`, `localstorage`, `react`, `billing`, `whatsapp` |

---

## Features

### Documents
- **Invoices** — create, edit, status (draft / sent / partial / paid / overdue)
- **Quotations** — proposals with validity dates; convert to invoices
- **Credit & debit notes** — adjustments linked to invoices (Issue & apply)
- **Recurring templates** — schedule repeated invoices

### Catalog
- **Customers** — contact details, multi-company assignment
- **Products & inventory** — SKU, price, stock, unit, custom product columns
- **Line-item custom columns** — add/rename columns on invoices & quotations (e.g. Brand, Color); included in PDF

### Export & share
- **PDF download** — branded templates (Classic, Modern, Minimal, Elegant, Corporate, Sunset, Monochrome, …)
- **Word (.rtf)** export
- **CSV / Excel** export for lists
- **WhatsApp Web** — open chat with pre-filled message + prepared PDF
- **Email** — open mail client with prepared message

### Payments & reports
- Record payments, mark paid / partial / unpaid
- Balance due with credits, debits, and payments
- Simple reports and dashboard stats

### Other
- Multi-currency support
- Multi-company (optional)
- Bulk select & delete on lists
- Google Sheets sync (optional OAuth)
- Fully client-side — works offline after first load

---

## Quick start

1. Download [`invoice-manager.html`](./invoice-manager.html)
2. Open the file in a modern browser (Chrome, Edge, Firefox, Safari)
3. Start creating invoices — no install, no account required

> **Tip:** For WhatsApp Web and some browser APIs, serve the file over `http://localhost` instead of `file://`:
> ```bash
> python -m http.server 8765
> # then open http://127.0.0.1:8765/invoice-manager.html
> ```

---

## Data storage

All data is stored in the browser **localStorage** under keys prefixed with:

```text
invoice-manager:ledger:*
```

Examples: invoices, clients, products, settings, companies.

- Clearing site data removes your records
- Use **CSV / Excel export** or Google Sheets sync for backups
- Data is private to this browser / device unless you export or sync

---

## Custom columns (line items)

On an invoice or quotation edit screen:

1. Under **Products / Services**, click **Add column**
2. Click a column title to rename it (Description, Qty, Rate, Amount, or custom names)
3. Enter values per line
4. **Done editing** → columns appear on the document view and in the **PDF**

---

## Credit & debit notes

| Type | Effect on linked invoice |
|------|---------------------------|
| **Credit note** | Reduces balance due |
| **Debit note** | Increases balance due |

Create a note → link an invoice (optional) → **Issue & apply**.

Balance formula:

```text
Balance due = Invoice total − Payments − Credits + Debits
```

---

## Tech stack

- React 18 (embedded in a single HTML file)
- Tailwind CSS
- Client-side PDF generation
- localStorage persistence
- Optional Google Identity / Sheets integration

No build step. Edit the HTML file or open it as-is.

---

## Browser support

Chrome, Edge, Firefox, and Safari (recent versions).  
Use a local HTTP server if `file://` limits downloads or WhatsApp Web.

---

## License

Choose a license when you create the GitHub repo (e.g. MIT).

---

## Contributing

Issues and pull requests are welcome. Please describe the feature or bug clearly and test in a major browser before submitting.
