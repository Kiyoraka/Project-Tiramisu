# MISU · Ordering System

> Handmade tiramisu, fresh daily, delivered cold across the **Klang Valley**.
> *Made with cocoa & care.*

MISU is an online ordering system for **MISU Desserts Enterprise**, a Petaling Jaya–based tiramisu shop. This repository currently holds the **interactive design prototype** (`index.html`) — a clickable, self-contained mockup of both the customer storefront and the owner's admin dashboard. It is the visual and functional reference for the production build.

---

## What's in here

| File | Description |
|------|-------------|
| `index.html` | Self-contained single-file prototype (≈2.9 MB). All HTML, CSS, JS, fonts, and images are embedded — no server, no install, no internet required. Just open it in a browser. |

### How the prototype loads
`index.html` is a **bundled single file**. On open, an inline loader script decodes the embedded assets (base64 + gzip) into in-memory `blob:` URLs, rebuilds the page, and mounts a **React** app transpiled in-browser via Babel. It runs entirely client-side — even from `file://`.

A toolbar at the top of the prototype lets you switch between:
- **Customer** ⇄ **Admin** views
- **Desktop** ⇄ **Mobile** layouts

---

## The Product

### 🛍️ Customer storefront
A mobile-first ordering experience:

- **Home** — hero, brand story, trust stats (*4,800+ boxes delivered*), and quick "track my order" by phone number.
- **Menu** — browse by category (All · Tiramisu · Drinks), add items to cart.
- **Cart** — slide-out drawer with quantity controls and live subtotal.
- **Checkout**
  - Choose **Delivery** (+RM5, Klang Valley) or **Self-pickup** (free, PJ kitchen)
  - Enter name, phone, and (for delivery) address
  - **Pay by bank transfer** and **upload a transfer slip** (screenshot/photo)
- **Success** — order confirmation while the slip is reviewed.
- **Track** — enter phone number to see live order status on a visual timeline.

#### Menu
| Item | Category | Price | Note |
|------|----------|-------|------|
| Classic Tiramisu | Tiramisu | RM18.90 | Bestseller |
| Mini Tiramisu Cup | Tiramisu | RM10.90 | Single serve |
| Signature Family Tub | Tiramisu | RM34.90 | Limited · serves 4–5 |
| Iced Chocolate | Drinks | RM9.50 | |
| Hot Chocolate | Drinks | RM8.50 | |

#### Payment
Manual bank-transfer flow with slip verification:
- **Account:** MISU Desserts Enterprise · Maybank · `5621 4478 9012`
- **Reference:** customer's phone number
- Orders are only prepared **after** the owner verifies the uploaded slip.

### 🧑‍🍳 Admin dashboard (owner)
Order and payment management for the shop owner:

- **Dashboard** — KPIs: orders today, verified revenue, slips awaiting verification, orders in the kitchen.
- **Orders** — full order list with filters (All · New · To verify), customer details, and status.
- **Payments** — review uploaded transfer slips, then **Verify** or **Reject** (reject requests a clearer re-upload).
- **Order detail** — view the slip/receipt (lightbox), verify payment, and **advance order status** through the fulfillment flow.

### 📦 Order lifecycle
```
Order placed → Payment verified → In the kitchen → Out for delivery → Delivered
```
Payment states: **Awaiting review → Verified / Rejected**.

---

## Contact (in-prototype)
- **Phone:** 012-345 6789
- **Email:** hello@misu.my
- **Social:** @misu
- **Hours:** Tue–Sun, 11am – 7pm · PJ Kitchen pickup

---

## Tech (prototype)
- **React 18** (`ReactDOM.createRoot`) with **Babel Standalone** for in-browser JSX — no build step.
- **State-based navigation** (no router) with a lightweight global store.
- **`localStorage` persistence** (key `misu_state_v4`) with seeded demo orders.
- **Fully offline** single-file bundle; demo imagery from Pexels with embedded fallbacks.

> ⚠️ **Prototype only.** There is no backend — all orders, payments, and verification are simulated in the browser for demonstration. The production system will be built as a proper application with a real backend, database, and secure payment-slip handling.

---

*MISU Desserts · Klang Valley · © 2026*
