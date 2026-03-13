# Sunday Toffee

Small batch, handmade toffee — made one batch at a time on weekends in San Francisco.

**Live site:** [sundaytoffee.com](https://sundaytoffee.com)

## What This Is

This is the website and order system for Sunday Toffee, a one-person toffee business started in February 2026. Customers can browse the site, learn about the product, and place orders for pickup (or delivery for orders $50+) in San Francisco.

## How It Works

The ordering flow goes like this:

1. Customer visits `index.html` (the homepage) and clicks "order some"
2. They fill out the order form on `order.html`, choosing quantities, pickup/delivery, and payment method
3. On submit, the form sends data to a Google Apps Script endpoint that logs the order to a Google Sheet and sends confirmation emails to both the customer and the owner
4. The customer is redirected to `thank-you.html` with their order summary

Orders are tracked in a [Google Sheet](https://docs.google.com/spreadsheets/d/1aMYtfGj0XfVVPL3K4x8bwcwLXIduO9J9GlLmNSF7dRY/edit?gid=1316233894#gid=1316233894) with columns for order details, pickup/delivery info, and checkboxes for "Picked Up?" and "Paid?" status.

## File Structure

```
sundaytoffee/
├── index.html          # Homepage — hero, product photos, reviews, about section
├── order.html          # Order form — quantities, customer info, pickup/delivery, payment
├── thank-you.html      # Post-order confirmation page with order summary
├── apps-script.txt     # Google Apps Script (doPost) that handles form submissions
├── CNAME               # Custom domain config for GitHub Pages (sundaytoffee.com)
├── images/
│   ├── sketch.png      # Hand-drawn hero illustration
│   ├── brown-box.png   # Product photo (chocolate almond toffee box)
│   ├── vday-1.png      # Valentine's Day promo image
│   └── vday-2.png      # Valentine's Day promo image
└── README.md
```

## Tech Stack

- **Frontend:** Plain HTML, CSS, and vanilla JavaScript (no frameworks, no build step)
- **Fonts:** Google Fonts — Libre Baskerville (headings) + Inter (body)
- **Order backend:** Google Apps Script deployed as a web app, writing to Google Sheets
- **Email:** Gmail (via Apps Script) — sends confirmation to customer + notification to owner
- **Analytics:** Google Analytics (GA4, tag `G-N0W7M8F5X0`)
- **Hosting:** GitHub Pages with custom domain (`sundaytoffee.com` via CNAME)
- **Payment:** Venmo (@oats123), Zelle, or cash at pickup

## Deployment

The site is hosted on GitHub Pages. Any push to the main branch deploys automatically.

To run locally, just open `index.html` in a browser. No server or build step needed. (Note: form submissions won't work locally since they POST to the Google Apps Script endpoint.)

### Updating the Google Apps Script

The Apps Script code lives in `apps-script.txt` for reference. To update the actual running script:

1. Open the Apps Script editor linked to the Google Sheet
2. Paste the updated code
3. Deploy as a new version (Manage Deployments → New Deployment)
4. Update the `SCRIPT_URL` in `order.html` if the deployment URL changes

## Products & Pricing

- **8 oz box** — $10
- **4 oz box** — $5
- Free delivery for orders $50+ within San Francisco

Ingredients: Butter, sugar, milk chocolate, almonds, walnuts, pecans, vanilla extract. Contains milk, soy, and tree nuts.

## Pickup & Delivery

- **Pickup:** Sundays at 3639 Market Street, San Francisco, CA 94131 (Upper Market). Windows are 2–3 PM or 3–4 PM.
- **Delivery:** Available for orders $50+, delivered 12–1:30 PM on Sundays within SF.
- Orders by Saturday 3 PM help with planning, but it's flexible.

## Contact

- **Text:** 510-621-7820
- **Instagram:** [@sunday_toffee](https://instagram.com/sunday_toffee)
- **Google Reviews:** [Leave a review](https://maps.app.goo.gl/P2sAxcqiENHMZJe37)
