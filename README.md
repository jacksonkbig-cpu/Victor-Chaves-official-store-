# Victor Chaves Official Store
## Premium Music & Video DVD E-Commerce Marketplace

### What's Included
A complete, production-ready single-page e-commerce application with:

**Storefront**
- Responsive hero section with live concert photos
- Product catalogue with 6 seeded products (Blu-ray, DVD, 4K UHD, Vinyl LP, Box Sets)
- Smart search and category filtering
- Product detail pages with image galleries, tracklists, and specs
- Shopping cart with quantity management
- Secure checkout with configurable payment methods
- Order tracking by order number + email
- Customer account system (register/login)
- Contact/inquiry form
- Multilingual support (English + Portuguese)

**Admin Dashboard**
- Admin login (email: oficialvictorchaves@gmail.com)
- First-time password setup
- Dashboard overview with sales stats, low-stock alerts
- Product Management: add, edit, delete products, set prices, manage stock
- Order Management: view orders, update order status
- Payment Methods: enable/disable methods, edit names and instructions
- Customer Inquiries: view and resolve contact messages
- Analytics: revenue, orders, customers, sales charts
- Settings: change currency, language, admin password

**Data Persistence**
The supplied original application stores products, orders, inquiries, payment methods, settings, cart and sessions in browser localStorage. This is a frontend-only demo, not server-backed production checkout.

### How to Use
1. Open `index.html` in a modern browser or deploy the folder as a static site.
2. Browse products, add items to cart and use the checkout demo.
3. Open `/#/admin` for the admin dashboard.
4. Admin email: `oficialvictorchaves@gmail.com`.
5. Set a password on first admin login.

### Payment Methods (Admin Configurable)
- Bank Transfer
- PayPal
- Credit Card (Stripe-ready)
- MB WAY
- PIX

### Production Requirements
The supplied project is frontend-only. Before accepting real orders/payments, connect a server-side database, secure server-side authentication, payment-provider APIs, and email delivery. Browser localStorage is not a shared order database.

### File Structure
```
index.html
styles.css
app.js
images/                 # Original product and artist photos
README.md
```

### Tech Stack
- Vanilla HTML5, CSS3, JavaScript (ES6+)
- No build step required
- No external dependencies
- Hash-based client-side routing
- CSS Custom Properties for theming

### Security Note
Admin authentication and data storage in the supplied archive are client-side. Do not use this demo as a production payment or authentication system without a secure backend.
