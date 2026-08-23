# NorCal Website

The official one-page website for NorCal, a Calgary-founded software and technology company serving small businesses across Canada. It is designed as a credible, conversion-focused destination for prospects arriving from direct outreach.

## Tech stack

- Semantic HTML
- Modern CSS
- Small amount of vanilla JavaScript
- No frameworks, packages, tracking scripts, build tools or runtime dependencies

## File structure

```text
norcal-website/
├── index.html                    Page content, metadata and JSON-LD
├── styles.css                    Complete responsive visual system
├── script.js                     Accessible mobile menu and current year
├── robots.txt                    Search crawler instructions
├── sitemap.xml                   Canonical homepage sitemap
└── assets/
    ├── norcal-logo.svg           Navbar/footer logo
    ├── favicon.svg               Browser icon
    ├── norcal-social-preview.svg Editable social image source
    └── norcal-social-preview.png Production Open Graph image
```

## Run locally

1. Download or clone the project.
2. Open `index.html` in a modern browser.

There is no build step. A simple local server such as VS Code Live Server is optional, not required.

## Replace the temporary logo

The original logo image was not present in the supplied attachment folder, so `assets/norcal-logo.svg` and `assets/favicon.svg` are clearly marked temporary monogram placeholders.

1. Export the production mark with a square view box and optimized file size.
2. Replace `assets/norcal-logo.svg` and `assets/favicon.svg`, keeping the existing names to avoid HTML changes.
3. Update `assets/norcal-social-preview.svg`, then regenerate the PNG at 1200 × 630.
4. Confirm the `logo` URL in the JSON-LD inside `index.html` still matches the final file.

## Customize founder information

Search `index.html` for `TODO:`. Each founder has clearly marked fields for biography, education, previous experience, technical expertise and skills.

### Add founder photographs

1. Prepare consistent, compressed portraits at approximately 900 × 1200 pixels.
2. Save them as `assets/abijeet.jpg` and `assets/gurman.jpg`.
3. Replace each `.founder-photo` placeholder `<div>` with an image. Example:

```html
<img
  class="founder-photo"
  src="assets/abijeet.jpg"
  width="900"
  height="1200"
  loading="lazy"
  alt="Abijeet Dhillon, Co-Founder of NorCal"
>
```

Keep explicit dimensions, `loading="lazy"` and meaningful alt text. The CSS class already provides the intended sizing; add `object-fit: cover` if the crop needs adjustment.

## Add previous work

Search `index.html` for `TODO: Add Project`. For each project:

1. Replace `[Project type]` with an accurate label such as `NorCal Client Work`, `Founder Experience` or `Personal Project`.
2. Add the project name and short description.
3. Replace `[Technologies / services]` with a concise list.
4. Replace the `.project-visual` placeholder with a compressed image using a 4:3 aspect ratio, explicit width and height, `loading="lazy"` and descriptive alt text.
5. Optionally add a website or GitHub link only when one is appropriate and public.

Do not present personal, academic or pre-NorCal work as NorCal client work.

## Change services or pricing

- Service copy is in the `#services` section of `index.html`; each item uses `.service-item`.
- The Website Improvement Package follows the four service items in the same section.
- Search for `Starting at` and `$500` to change the starting price. Keep this language unless pricing has formally changed, because it does not imply a flat rate.
- Package scope and pricing qualifications are in `.offer__details`.

## Contact information

Email addresses and phone numbers appear in four places: navigation/CTA mail links, founder profiles, the contact section and the footer. They also appear in the JSON-LD near the top of `index.html`.

When contact details change, search the entire project for the old value. Keep visible phone formatting human-readable and `tel:` values free of punctuation.

## SEO configuration

`index.html` contains:

- Page title and meta description
- Canonical URL
- Open Graph and Twitter card tags
- Organization/service JSON-LD
- Semantic headings and crawlable anchor navigation

Also review:

- `robots.txt` for crawler access and the sitemap location
- `sitemap.xml` for the canonical homepage URL
- `assets/norcal-social-preview.png` for the 1200 × 630 social image

After major content changes, test the page with Lighthouse and validate the structured data using Google’s Rich Results Test or Schema.org validator.

## Deploy to Vercel

### Option A: GitHub import

1. Push this folder to a GitHub repository.
2. In Vercel, choose **Add New → Project** and import the repository.
3. Leave the framework preset as **Other**.
4. Leave the build command empty and use the repository root as the output directory.
5. Deploy.

### Option B: Vercel CLI

If the Vercel CLI is already installed, run `vercel` from this folder and follow its prompts. No build settings are required.

### Connect `norcal.ca`

In the Vercel project, open **Settings → Domains**, add `norcal.ca`, and follow Vercel’s displayed DNS instructions at the domain registrar. Add the preferred `www` redirect if desired. DNS values vary, so use the current values Vercel provides.

## Final production checklist

- [ ] Replace the temporary logo and favicon with the supplied production assets
- [ ] Add and compress founder images
- [ ] Complete both founder biographies, education, experience and skills
- [ ] Populate all three previous-work entries with accurately labelled projects
- [ ] Confirm founder phone numbers
- [ ] Confirm all email addresses and links
- [ ] Test every consultation CTA and `mailto:` link
- [ ] Verify the favicon in major browsers
- [ ] Keep all new images compressed and explicitly sized
- [ ] Test continuously across mobile, tablet and desktop widths
- [ ] Check portrait and landscape orientations
- [ ] Test the keyboard-accessible mobile navigation
- [ ] Run Lighthouse for performance, accessibility, best practices and SEO
- [ ] Validate JSON-LD structured data
- [ ] Verify `sitemap.xml`
- [ ] Verify `robots.txt`
- [ ] Connect and verify `norcal.ca` in Vercel
- [ ] Test the deployed site on iOS Safari, Android Chrome and desktop browsers
