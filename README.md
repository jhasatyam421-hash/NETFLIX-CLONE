# Netflix Clone (Next.js + TypeScript)

This is a starter advanced Netflix-clone scaffold:
- Next.js + TypeScript
- Tailwind CSS
- Prisma + Postgres (Supabase friendly)
- NextAuth (Email provider) + Prisma adapter
- Stripe test wiring (checkout webhook placeholder)
- HLS playback simulation (react-player)
- Admin upload API placeholders

Quick start:
1. Install dependencies
   npm install

2. Copy .env.example -> .env and fill values (DATABASE_URL, NEXTAUTH_SECRET, STRIPE keys ...)
   - For local Postgres use: postgresql://user:pass@localhost:5432/dbname
   - If using Supabase, set DATABASE_URL from Supabase.

3. Generate Prisma client and migrate
   npx prisma generate
   npx prisma migrate dev --name init

4. Seed DB
   npm run prisma:seed

5. Run dev server
   npm run dev
   Open http://localhost:3000

Notes & next steps:
- Configure EMAIL_SERVER and EMAIL_FROM to enable NextAuth Email login.
- For Stripe: set STRIPE_SECRET_KEY and NEXT_PUBLIC_STRIPE_PK; implement full webhook handling in pages/api/stripe/webhook.ts.
- For HLS streaming: upload manifest (.m3u8) files to Cloudinary / S3 and set movie.hlsUrl to signed URLs.
- To push to GitHub: give me the target owner/repo and I will create a single commit and push.

If you want, I’ll:
- Expand the admin UI for uploads + signed URL generation
- Implement full Stripe checkout and webhook processing with subscription lifecycle
- Add multi-profile UI + My List + progress resume endpoints and UI
- Push to your GitHub repo (provide owner/repo and push access)