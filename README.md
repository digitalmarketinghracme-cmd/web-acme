# ACME Switchgears – Corporate Website

A responsive corporate website for ACME Switchgears, built with React, Vite, Express and PostgreSQL.

## Included
- Responsive home, company profile, products, brand partners, industries and contact sections
- ACME logo and manufacturer banner images referenced from the existing ACME website
- Product enquiry form with server-side validation
- Express REST API and PostgreSQL enquiry storage
- Security headers, CORS configuration and API rate limiting

## Requirements
- Node.js 18+
- PostgreSQL 14+ (for saving enquiries)

## Run locally
1. Extract the ZIP and open the project folder.
2. Install dependencies: `npm install`
3. Copy `.env.example` to `.env`.
4. Set `DATABASE_URL` to your PostgreSQL connection string.
5. Start both frontend and backend: `npm run dev`
6. Open `http://localhost:5173`.

The API runs on port 5000. Vite forwards `/api` requests to the API only when a proxy is configured; for local development, add this `server` block to `vite.config.js` if needed:

```js
server: {
  port: 5173,
  proxy: { '/api': 'http://localhost:5000' }
}
```

## Production
- Set `CLIENT_ORIGIN` to your production website origin.
- Set `DATABASE_URL`.
- Run `npm run build`.
- Run `npm start` with `NODE_ENV=production`.
- Deploy behind HTTPS.

## Image and brand asset note
The site references the current ACME website's published logo and brand banner image URLs. Keep the source website's media URLs available, or download those images into a local `/public/assets` folder and update the URLs before deployment if you need fully self-hosted assets.

## Enquiry database
The API automatically creates the `enquiries` table when it starts and a database connection is configured. If PostgreSQL is not configured, the website remains viewable but enquiry submission returns a setup message. Phone, email and WhatsApp contact links remain available.


## Online store integration
- The navigation and dedicated Shop Online section link to https://www.acmeswitchgears.net/.
- The Koino Sensors & Push Buttons card links to the supplied Koino product page.
- The attached ACME logo is included locally at `public/acme-logo.png`.
- Checkout, cart, payment, stock and order management remain on the external online store; this website links customers to it.
