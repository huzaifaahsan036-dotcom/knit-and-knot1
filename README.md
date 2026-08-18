# Knit & Knot

Production-oriented Next.js + TypeScript + Tailwind + Supabase storefront for the Knit & Knot handmade accessories brand.

## Requirements
- Node.js 22+
- npm
- Supabase project

## Run locally
1. Create `C:\Projects\KnitAndKnot` and copy this project there (the included source is portable).
2. Copy `.env.example` to `.env.local` and add your Supabase URL and anon key.
3. In Supabase SQL Editor, run `supabase/schema.sql`.
4. Create a Supabase Storage bucket named `product-images` and configure admin-only upload/delete policies as needed.
5. `npm install`
6. `npm run dev`

## Admin
After creating your first account, promote that user's `profiles.role` to `admin` directly in the Supabase dashboard/SQL editor. Normal customers cannot promote themselves because the profile update policy only permits a customer role for self-updates.

## Logo
The supplied Knit & Knot logo is included as `public/logo.jpg` and is used in the header and hero.

## Notes
- No real payment gateway is implemented yet; orders are placed through the transactional `create_order` RPC and can be manually managed by admins.
- Product/category/order data is Supabase-backed; the app does not use a permanent hard-coded product array.
- Keep the Supabase service-role key server-side only.
