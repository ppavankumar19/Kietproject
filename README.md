# AI Karyashala Bootcamp — Student Testimonials

A single-page, static web experience that pulls real student reviews from Supabase Storage and presents them with animated stats, pagination, and a “show 10 random reviews” shuffle mode.

## What’s Inside
- Hero section with animated total review count and average rating (and live star display).
- Responsive testimonial cards with highlighted review text and student meta info.
- Randomize mode to quickly preview 10 shuffled reviews; reset to full paginated view.
- Pagination UI with fixed early pages plus ellipsis handling for large datasets.
- Graceful loading/error states and SVG fallback avatars if images fail.

## Data & APIs
- Supabase project: `pwghpxxfejmxvwhdjkda.supabase.co`
- Public anon key is inlined in `index.html` (intended for client-side/public use).
- Data file: Storage bucket `data/students_data.json`
- Images: Storage bucket `student-images/` (public URLs resolved per student record).

## Run Locally
Because it’s a static page, you only need a tiny web server so browser CORS rules stay happy:
- With Node: `npx serve .` (or `npx http-server .`)
- With Python 3: `python3 -m http.server 8000`
- Then visit `http://localhost:8000/index.html`

## Customizing
- Swap Supabase project or buckets by updating `SUPABASE_URL` and `SUPABASE_ANON_KEY` in `index.html`.
- Change per-page count via `PER_PAGE` constant (default 10).
- Update colors/spacing in the `:root` CSS variables near the top of `index.html`.

## Project Structure
- `index.html` — full page markup, styles, and Supabase-backed data loading logic.
- `README.md` — you’re reading it.

## Deployment (Vercel)
- Prereqs: Vercel account and Vercel CLI (`npm i -g vercel`).
- One-time setup from the project root: run `vercel`, choose “Other” framework, leave build command empty, set output directory to `.`.
- Deploy updates: `vercel deploy --prod` (serves the current working tree as a static site).
- No env vars required; the Supabase anon key is public and inlined for client-side use.

## Live Demo
- Deployed on Vercel: https://kietproject-gqpiuxfe5-pavan-kumar-s-projects-a55a3b6a.vercel.app/
