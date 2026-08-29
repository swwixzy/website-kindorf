# KINDORF Website

A first-stage marketing/intake site for KINDORF, based on the project brief.

## Structure

```
my-site/
├── index.html      # all sections: Home, About, Projects, Submit a Project, Join, Partnerships, Departments
├── style.css       # design tokens, layout, scroll-reveal animations
├── script.js       # mobile nav, scroll-reveal, EN/RU language switch, form handling
├── images/
│   ├── logo.png    # the KINDORF logo you provided
│   └── photo.jpg   # generated placeholder graphic (organic branching motif echoing the logo's "K")
└── README.md
```

Just open `index.html` in a browser — no build step required.

## What's included

- **Home** — short intro, tagline (Connect · Create · Impact), primary calls to action.
- **About Kindorf** — organization purpose, principles, and working model, based on your description.
- **Projects** — card layout with name, short description, Project Owner, geography, direction, status, and a "view details" link. Populated with **placeholder sample entries** — swap these for real project data (ideally pulled from a small database or CMS so non-public fields can stay hidden).
- **Submit a Project** — form with all the fields you listed (name, project name, description, goal, geography, direction, what's done, help needed, email).
- **Join Kindorf** — a starter form (name, email, department of interest, note) — the field list is flagged in your brief as still to be defined, so treat this as a draft.
- **Partnerships** — a starter form for organizations (organization name, email, proposed collaboration) — also a draft pending your input.
- **Departments** — grid of IT, SMM, Partnerships, International Relations, each with a "Department Lead" placeholder.

## Design notes

- Palette: deep forest green + white/cream, with a sage accent — kept close to your request while staying legible and calm rather than loud.
- Type: Fraunces (a warm, slightly organic serif) for headings to echo the flowing "K" in your logo; Work Sans for body copy.
- Signature detail: a thin vine-like line running down the left edge of the page (desktop only) that "grows" as you scroll — a nod to the logo's branching K strokes and the "grow an idea" theme.
- Scroll animations: sections and cards gently fade/rise into view as you scroll (respects `prefers-reduced-motion` for accessibility).
- Fully responsive, with a mobile menu.

## Bilingual EN/RU

Every translatable string carries both `data-en` and `data-ru` attributes, and the **EN / RU** toggle in the header switches all of them instantly (no reload, no separate pages). This is a genuinely workable first-stage approach:

- **Pro:** one HTML file, one URL, easy to maintain, real multilingual support from day one.
- **Trade-off:** it's a client-side swap, not separate localized URLs — so it won't give you per-language SEO (e.g. distinct indexable `/ru/` pages). If SEO across both languages matters later, migrate to real localized routes (e.g. Next.js i18n routing or two static builds) — the copy is already split by language, so migration is mostly restructuring rather than retranslating.

## What's not wired up yet (by design, per your "keep it simple" note)

- **Submit a Project / Join / Partnerships forms** currently show a confirmation message but don't send anywhere. To get submissions into your email, the simplest options are:
  - A form backend service (e.g. Formspree, Getform) — a few lines of config, no server needed.
  - A small serverless function (e.g. on Vercel/Netlify) that emails you on submit.
- **Project data** is hardcoded sample content — worth moving to a simple JSON file or lightweight CMS once you're ready, so you can add/hide projects without touching the code, and so non-public fields never reach the page's HTML at all.
- **Department Lead** names are placeholders — just replace the text once you have the list.

## Next steps

1. Swap in real project entries and department leads.
2. Decide on the Join Kindorf and Partnerships form fields, then I can extend the forms.
3. Pick a form backend (or I can wire up a simple serverless email handler).
4. If desired, split into real `/en/` and `/ru/` routes for SEO.
