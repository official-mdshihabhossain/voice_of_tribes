# Voice of Tribes — Path A starter

Free-first architecture: Cloudflare Pages + Workers + D1 + GitHub + Google Drive.

## What is included
- Responsive public website: Home, Stories, Gallery, Team, Contact, Account
- English/Bangla UI switch (content is structured for either language)
- User registration/login with password hashing using Web Crypto
- Profile fields with public visibility controls
- Story submission with Pending status
- Admin dashboard with Story/Team/Gallery sections
- Story status workflow: pending, review, approved, published, rejected
- Media URLs including Google Drive share links
- SEO: sitemap, robots, Open Graph, JSON-LD
- D1 schema and Worker API

## Important security note
This is a real starter application, but before public launch you should configure production secrets, restrict admin accounts, test file/media permissions, enable Cloudflare Turnstile, and make regular D1 exports/backups. Do not put private Google Drive links into public stories.

## Deploy outline
1. Create a GitHub repository and upload this project.
2. Create a Cloudflare Pages project connected to the repo.
3. Deploy `public/` as the static output.
4. Create a Cloudflare Worker from `worker/` and bind a D1 database named `DB`.
5. Run `db/schema.sql` in D1.
6. Set Worker environment variables `ADMIN_EMAIL` and `ADMIN_PASSWORD_SETUP_TOKEN` only for initial setup.
7. Change the admin password immediately after creating the admin account.
8. Set `API_BASE_URL` in `public/js/config.js` to the Worker URL.

The included code is intentionally simple so a beginner can understand and modify it.
