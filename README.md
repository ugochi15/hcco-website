# HCCO Website

Website for **Heaven Children Care Organization (HCCO)** — a faith-rooted nonprofit dedicated to nourishing, supporting, and empowering vulnerable children and families through food assistance, education, care, and community partnerships.

Plain HTML/CSS/JS static site, deployed free on GitHub Pages. No build step — just edit the `.html` files directly and push.

## Structure

```
index.html          Home
about.html           About Us
programs.html        Our Programs
impact.html          Our Impact
get-involved.html    Get Involved
donate.html          Donate
contact.html         Contact Us
assets/css/style.css Shared styling
assets/js/script.js  Mobile nav + small behaviors
assets/img/          Photos (currently placeholders)
```

Every page shares the same header/footer, copy-pasted at the top and bottom of each file (no templating system, so edits to the header/footer must be made on every page).

## Editing content

Just open any `.html` file in a text editor and edit the text between tags. To find every placeholder still needing real content, search the project for `[` and `TODO` and `placeholder` — every one is a spot marked for real HCCO info.

## Before launch — checklist

- [ ] **Our Story** (about.html) — replace with the real founding story
- [ ] **Vision statement** (about.html)
- [ ] **Core Values** descriptions (about.html)
- [ ] **Our Faith** section (about.html)
- [ ] **Leadership & Trustees** — real names, titles, photos (about.html)
- [ ] **CAC registration number** (about.html, footer on every page)
- [ ] **Programs** — confirm which of the 4 programs are Active vs Planned, add real specifics (programs.html)
- [ ] **Impact numbers** — children reached, meals provided, communities reached, volunteers (index.html, impact.html)
- [ ] **Testimonials / stories** — real, permission-cleared quotes (index.html, impact.html)
- [ ] **Photos** — replace all placeholder boxes with real photos (ideally with consent, especially photos of children)
- [ ] **Social media links** (contact.html footer + Follow Us card)
- [ ] **Location / address** (contact.html)
- [ ] **Donate button** — connect a real Stripe Payment Link (see below)
- [ ] **Contact form** — connect a real Formspree endpoint (see below)

## Connecting donations (Stripe)

1. Create a free account at [stripe.com](https://dashboard.stripe.com/register) (needs HCCO's bank details for payouts).
2. In the Stripe Dashboard, go to **Payment Links → + New**, set it up for a donation (fixed amount or "customer chooses amount"), and save.
3. Copy the generated link (looks like `https://buy.stripe.com/xxxxxxx`).
4. In `donate.html`, find `#TODO-stripe-link` and replace it with your real link.
5. Repeat for recurring/monthly giving (`#TODO-stripe-recurring-link`) once you're ready — Stripe Payment Links support subscription pricing too.

## Connecting the contact form (Formspree)

1. Create a free account at [formspree.io](https://formspree.io) (50 submissions/month free).
2. Create a new form, copy its endpoint (`https://formspree.io/f/xxxxxxx`).
3. In `contact.html`, replace `YOUR_FORM_ID` in the form's `action` attribute with your real endpoint.

## Deploying changes

The site is deployed on GitHub Pages. To publish any edit:

```
git add .
git commit -m "Update site content"
git push
```

GitHub Pages rebuilds automatically within a minute or two of every push to `main`.

## Adding a custom domain later

Once ready to spend ~$12–15/year on a real domain (e.g. `heavenchildrencare.org`):

1. Buy the domain from any registrar (Namecheap, Google Domains successor, etc.).
2. Add a `CNAME` file to the project root containing just the domain name.
3. In the registrar's DNS settings, point the domain at GitHub Pages (an `A` record to GitHub's IPs, or a `CNAME` record to `ugochi15.github.io` for a subdomain).
4. In the GitHub repo's Settings → Pages, enter the custom domain.

No other changes to the site are needed — this is a DNS/hosting config step only.
