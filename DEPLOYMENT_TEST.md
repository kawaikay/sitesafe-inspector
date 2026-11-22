# SiteSafe Inspector Commercial MVP v3 - Deployment Test

## Upload
Replace the root files in the `sitesafe-inspector` GitHub repository with this package. Keep the folder `icons/`. GitHub Pages should redeploy automatically.

## First-time test
1. Open `https://kawaikay.github.io/sitesafe-inspector/` online.
2. Create a SiteSafe account using an email address that can receive confirmation mail.
3. Confirm the email, then sign in.
4. The licence panel should appear because no subscription exists yet.
5. Click Subscribe HK$38/month and use exactly the same email during Stripe Checkout.
6. Return to SiteSafe and click `I have paid - Refresh licence`.
7. The inspection interface should open after the Stripe webhook writes an `active` row linked to the Supabase user.

## Expected database result
`public.subscriptions.user_id` matches the authenticated `auth.users.id`; `status` is `active` or `trialing`; `offline_license_until` is in the future.

## Important limitation
If a customer pays before creating a SiteSafe account, the current webhook cannot attach the payment to a Supabase `user_id`. Require account creation and email confirmation before checkout.

## Security
The browser contains only the Supabase Project URL and publishable key. Never add the Supabase service-role/secret key, database password, Stripe restricted key, or Stripe webhook signing secret to these files.
