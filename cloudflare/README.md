# Short & Sweet shared orders backend

This folder contains the Cloudflare Worker + D1 database used by the website.

## One-time Cloudflare setup

1. Create a D1 database named `short-sweet-orders`.
2. Run the SQL in `schema.sql` in the D1 console.
3. Create a Worker named `short-sweet-api`.
4. Paste `worker.js` into the Worker.
5. Add a D1 binding:
   - Variable name: `DB`
   - Database: `short-sweet-orders`
6. Add a Worker secret named `ADMIN_KEY` with a strong private password.
7. Deploy the Worker.
8. Copy its `https://...workers.dev` URL.
9. Put that URL into the root `config.js` file:
   `window.SHORT_SWEET_API = "https://YOUR-WORKER.workers.dev";`

Once that URL is set, checkout/admin/tracking use the same shared online database across devices.
