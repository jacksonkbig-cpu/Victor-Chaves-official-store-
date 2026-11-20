# Victor Chaves Official Store

Premium music and video e-commerce storefront for Victor Chaves.

## Included in the original project archive

- `index.html` — application shell and page layout
- `styles.css` — responsive dark-theme styling
- `app.js` — storefront, customer account, cart, checkout screens, order tracking, contact form, and admin interface
- `images/` — 21 supplied product and artist images

The application is written in vanilla HTML, CSS, and JavaScript. It has no build step or package dependencies and uses hash-based client-side routing. Open `index.html` in a browser to run the standalone demo.

## Storefront features

- Responsive hero section and product catalogue
- Search and category filtering
- Product details, galleries, tracklists, and specifications
- Shopping cart and checkout screens
- Order lookup by order number and email
- Customer registration and sign-in screens
- Contact/inquiry form
- English and Portuguese interface

## Admin interface

- Admin route: `/#/admin`
- Store administrator email: `oficialvictorchaves@gmail.com`
- First-time password setup is prompted by the frontend

The original admin login and data are implemented in browser JavaScript and browser storage. This is not server-side authentication.

## Important: current security and payment limitations

**This archive is a frontend demo, not a production-ready e-commerce system.**

The original application stores products, orders, inquiries, payment settings, cart state, customer sessions, and admin credentials in browser `localStorage`. Browser-side data and password checks are not secure and are not shared reliably between customers or devices.

The checkout screens do not by themselves process payments. Listing Stripe, PayPal, MB WAY, PIX, or bank transfer as a payment option does not mean a live payment integration exists.

Do not collect real payment details, accept live orders, or rely on the browser-based admin login for production operations until a secure backend and payment provider integration have been implemented and tested.

The original archive also contains a separate credentials reference file with a plaintext password. That file is intentionally excluded from this repository and must never be published. Rotate that password anywhere it may have been reused.

## Cloudflare deployment status

The Cloudflare account currently has a static storefront Worker named `projeto-vc-ordem` and a separate admin/API Worker named `victor-chaves-admin`. On 2026-11-20, the admin Worker was rolled back to its earlier deployed version because the newer version had removed its required D1 binding. The active deployment is now version `8b091664-f7de-492b-8dd1-145196539a56` at 100% traffic, and that version declares the D1 binding `DB` to database `vc_store_data`.

The original browser application still uses `localStorage`; it has not yet been connected to those API routes. The separate admin Worker is protected by Cloudflare Access. The dedicated, non-reusable Access allow policy for `oficialvictorchaves@gmail.com` is attached to the Victor Chaves Admin Portal. A separate reusable policy for `theovonmanagement4@gmail.com` is still attached to this portal and is also shared with two other Cloudflare Access applications. It has intentionally not been deleted or modified because doing so could affect those other applications. The original frontend admin login also uses `oficialvictorchaves@gmail.com`, but it is browser-side demo authentication and is not the same as Cloudflare Access.

Consequently, the restored D1 binding repairs the admin Worker configuration, but the presence of the Workers and database does not mean the storefront is fully integrated with the backend. Complete and test the frontend/API integration before using the store for real customers.

## Payment methods shown in the original admin UI

- Bank Transfer
- PayPal
- Credit Card (described as Stripe-ready)
- MB WAY
- PIX

These are configurable UI options only unless separately connected to working payment services.

## Production work still required

1. Upload and deploy the complete original source archive, including all 21 images, to the storefront hosting project.
2. Connect storefront product, order, and inquiry operations to the D1-backed API.
3. Replace the browser-side admin demo login with server-side administrator authentication and authorization; keep Cloudflare Access restricted to the store administrator.
4. Add verified payment-provider integrations and server-side payment confirmation/webhooks.
5. Add server-side validation, rate limiting, spam protection, and appropriate data-retention controls.
6. Configure transactional email for order and inquiry notifications.
7. Test storefront, admin access, order flow, database persistence, and payment sandbox flows before launch.

## Original project structure

```
victor-chaves-store/
  index.html
  styles.css
  app.js
  images/          # 21 supplied images
  README.md
```
