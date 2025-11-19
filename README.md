# All In One - Quick Start

## Overview
This repository contains a Next.js + Tailwind starter for the All In One platform, with:
- NextAuth + Prisma scaffold
- Sanity Studio schemas
- Assistant API endpoint (proxy to OpenAI)
- Basic UI pages

## Quick Local Setup (simplified)
1. Install dependencies:
   ```
   npm install
   cd studio && npm install
   ```

2. Create `.env.local` with:
   ```
   DATABASE_URL=postgresql://USER:PASS@HOST:PORT/db
   NEXTAUTH_URL=http://localhost:3000
   NEXTAUTH_SECRET=a_random_secret
   GOOGLE_CLIENT_ID=...
   GOOGLE_CLIENT_SECRET=...
   EMAIL_SERVER=smtp://...
   EMAIL_FROM=you@domain.com
   NEXT_PUBLIC_SANITY_PROJECT_ID=your_project
   NEXT_PUBLIC_SANITY_DATASET=production
   SANITY_API_TOKEN=...
   OPENAI_API_KEY=sk-...
   ```

3. Prisma:
   ```
   npx prisma generate
   npx prisma migrate dev --name init
   ```

4. Run Sanity Studio (in studio/):
   ```
   npm run start
   ```

5. Run Next:
   ```
   npm run dev
   ```

## Deploy
- Push to GitHub and import repository in Vercel.
- Add environment variables in Vercel dashboard.
- Deploy.

## Notes
- The assistant endpoint proxies to OpenAI; keep your OPENAI_API_KEY secret.
- Customize and secure production configs before public launch.
