# ProBuilt Construction Website

Marketing website for **ProBuilt Construction**, a residential construction company serving Sullivan and Ulster Counties, NY. ProBuilt does high-end ground-up construction, full-home renovations, and smaller renovations. Founded in 2021.

Contact: (845) 481-1042 · office@probuiltny.com

## Pages

| Page | Purpose |
| --- | --- |
| Home | Hero, services (ground-up, full-home renovations, smaller renovations), approach, selected work, testimonials, call to action |
| Our Work | Photo gallery with a filter by area of the house (All, Ground-Up, Kitchens, Bathrooms, Living Spaces, Bedrooms) and a lightbox |
| About | Company story, how the team works, service area |
| Contact | Phone, email, service area, and what to include when reaching out |

## Design

- Brand colors from the logo: teal `#27BFC0` and charcoal grey `#545454`
- Font: Archivo (Google Fonts)
- Responsive layout (desktop, tablet, mobile)
- Gallery filter and lightbox are plain JavaScript, no framework required

## Project status

- [x] Design and layout for all four pages
- [x] Gallery with category filter and lightbox
- [x] Phone and email added
- [ ] Real client testimonials (currently bracketed placeholders)
- [ ] Legal entity name in the footer (`[LLC / INC]`)
- [ ] Contact form and backend (see below)
- [ ] Cloudflare hosting and domain
- [ ] SEO basics: page titles, meta descriptions, Open Graph image, sitemap
- [ ] Optimize and bundle photos for production

## Backend to-do

The site is currently static (no server code, no database). The only thing that needs a backend is a contact or quote-request form. Suggested scope:

1. **Contact form endpoint** that accepts name, email, phone, town, project type, and message
2. **Validation and spam protection** (honeypot field or CAPTCHA, rate limiting)
3. **Email delivery** to office@probuiltny.com, with an auto-reply to the sender
4. **Optional:** store submissions for record keeping
5. **Environment variables** for any API keys, never committed to the repo

Options, from least to most work: a hosted form service, a serverless function on the host, or a small custom API.

## Suggested repository structure

```
/
├── index.html
├── work.html
├── about.html
├── contact.html
├── assets/
│   ├── images/        # gallery and page photos
│   └── logo.svg
├── css/
├── js/
│   └── gallery.js     # filter and lightbox
├── api/               # backend / serverless functions (if used)
├── .env.example
└── README.md
```

## Local development

Add the commands for your setup here, for example:

```bash
# static preview
npx serve .
```

## Deployment

Hosted on **Cloudflare**. The site is static, so it deploys as plain files. Connect the GitHub repo in the Cloudflare dashboard, set the build output to the repo root (no build step needed), and add the custom domain there.

The contact form backend can run on Cloudflare as well (a Worker or Pages Function). Keep any API keys in Cloudflare environment variables or secrets, not in the repo.

## Content notes

- Gallery photos are real ProBuilt projects. Projects are labeled by category only, not by name.
- ProBuilt should not be positioned as a basement company. The message is high-end ground-up construction and full-home renovations.
- Tone: very high quality, hands-on, local work, with the team involved from beginning to end.
