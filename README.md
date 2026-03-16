# trg[README.md](https://github.com/user-attachments/files/26038645/README.md)
# TRG Resource Navigator - Launch Ready

This bundle is built so you can launch now and wire in your full database later.

## What is already in place
- Public landing page with value proposition and chatbot UI
- Working chatbot API
- Admin dashboard for adding, editing, bulk importing, and deleting resources
- Demo fallback dataset so the site still works before Supabase is connected
- Lead capture form for churches, nonprofits, and outreach teams
- Health check endpoint
- Render deployment file

## Brutal truth
A site is easy. Trust is hard.

If the data is stale, this tool becomes a liability. So this version is designed to let you launch a polished demo fast **without pretending you already have the full database solved**.

## Quick launch path
1. Upload this project to GitHub.
2. Deploy it to Render.
3. Set environment variables from `.env.example`.
4. Launch with demo data first.
5. Build your real resource database behind it.
6. Turn `USE_SUPABASE=true` after your table is ready.

## Local setup
```bash
npm install
npm start
```
Open:
- Landing page: `http://localhost:3000`
- Admin dashboard: `http://localhost:3000/admin.html`

## Environment variables
```env
PORT=3000
NODE_ENV=production
APP_NAME=TRG Resource Navigator
PUBLIC_BASE_URL=http://localhost:3000
ALLOWED_ORIGIN=http://localhost:3000
ADMIN_PASSWORD=replace-this-with-a-strong-password
LEAD_NOTIFICATION_EMAIL=
USE_SUPABASE=false
SUPABASE_URL=
SUPABASE_ANON_KEY=
```

## Demo mode vs database mode
### Demo mode
Set:
```env
USE_SUPABASE=false
```
The app will use `data/demo_resources.json`.

### Database mode
Set:
```env
USE_SUPABASE=true
SUPABASE_URL=...
SUPABASE_ANON_KEY=...
```
Then run the SQL in `supabase_schema.sql`.

## Supabase schema
Run `supabase_schema.sql` in the Supabase SQL editor when you're ready.

## Admin access
Open `/admin.html` and use the password from `ADMIN_PASSWORD`.

## Bulk import format
You can paste CSV or TSV with these columns:
- `organization_name`*
- `county`*
- `category`*
- `services`
- `address`
- `city`
- `state`
- `zip`
- `phone`
- `email`
- `website`
- `hours`
- `eligibility`
- `notes`
- `verified`

## Endpoints
- `GET /api/health`
- `POST /api/chat`
- `POST /api/leads`
- `POST /api/admin/login`
- `GET /api/admin/resources`
- `POST /api/admin/resources`
- `PUT /api/admin/resources/:id`
- `DELETE /api/admin/resources/:id`
- `POST /api/admin/resources/bulk`

## The next real upgrades
1. Replace password auth with Supabase Auth or Clerk.
2. Add user roles.
3. Add verification dates and assigned owner.
4. Add call notes and outreach tracking.
5. Add true AI search only after the data model is clean.

## Suggested launch message
Position it as:
**"A county-level resource navigator for churches, nonprofits, and outreach teams who need fast answers on food, housing, clothing, jobs, and assistance resources."**
