# EXAM TRACKER 2027

## Phase 1 update: Student onboarding
- Email OTP authentication
- Student profile onboarding: name, class, board, target exam
- Profile saved to Supabase `profiles`
- Dashboard greets student and displays their selected study path
- Profile can be edited from dashboard

## Setup
1. Install Node.js 20+ and run `npm install`.
2. Copy `.env.example` to `.env.local`, then add Supabase URL and anon key.
3. Run `supabase/schema.sql` in Supabase SQL Editor. If upgrading from the first ZIP, run the updated SQL too.
4. In Supabase Authentication > Providers > Email, enable email OTP and set the email template to show `{{ .Token }}`.
5. In Supabase Auth URL Configuration, add local and deployed URLs to allowed redirect URLs.
6. Run `npm run dev`.

## Deploy
Push to GitHub, import into Vercel, set the two Supabase environment variables, deploy, then configure the production URL in Supabase Auth.

## Production security
The admin page in this starter is not yet production-secure. Before launch, implement server-side role claims and matching RLS policies. Never expose the service-role key in browser code. Public exam/resource reads should be restricted to verified records. Do not publish unverified dates or copyrighted material without permission.
