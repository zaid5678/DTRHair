# DTRHair Website

Premium barbershop website for DTRHair — Newcastle and Durham branches.

Built with [Astro](https://astro.build) and Tailwind CSS.

## Tech Stack

- **Framework:** Astro (static site generation)
- **Styling:** Tailwind CSS v4 + custom CSS variables
- **Fonts:** Cormorant Garamond (headings) + DM Sans (body/UI) via Google Fonts
- **Booking:** Fresha integration (direct links) + enquiry form (Formspree)
- **Deployment:** Static — deploy to Netlify, Vercel, or any static host

## Development

```bash
npm install
npm run dev
```

Visit `http://localhost:4321`

## Build

```bash
npm run build
npm run preview
```

## Project Structure

```
src/
  components/
    Nav.astro        — Fixed navigation with mobile overlay
    Hero.astro       — Full-screen hero section
    About.astro      — About section with branch location cards
    Services.astro   — Services with branch tab switcher
    Team.astro       — Team grid (all barbers)
    Reviews.astro    — Client reviews grid
    Booking.astro    — Fresha CTAs + enquiry form
    Footer.astro     — Footer with branch info and social links
  data/
    newcastle.json   — Newcastle branch data
    durham.json      — Durham branch data
  pages/
    index.astro      — Main page (assembles all components)
  styles/
    global.css       — Global CSS variables, typography, utilities
public/
  favicon.svg
  images/            — Add barber photos here (optional)
```

## Owner Actions Required

### 1. Add Phone Numbers
Open `src/data/newcastle.json` and `src/data/durham.json` and replace the `"TODO: Add ... phone number"` strings with actual phone numbers.

### 2. Connect the Enquiry Form (Formspree)
1. Sign up at [formspree.io](https://formspree.io)
2. Create a new form and copy your form ID (e.g. `xabc1234`)
3. Open `src/components/Booking.astro`
4. Find `const FORMSPREE_ID = 'YOUR_FORM_ID';`
5. Replace `YOUR_FORM_ID` with your actual Formspree form ID
6. The form will then submit to your email inbox

### 3. Add Social Media Links
Open `src/components/Footer.astro` and replace the `href="#"` placeholders with actual Instagram, Facebook, and TikTok URLs.

### 4. Add Barber Photos (Optional)
1. Add portrait photos to `public/images/` (e.g. `dawud.jpg`, `tariq.jpg`, `raheem.jpg`, `zain.jpg`)
2. Update the `"image"` field in each barber object in the data JSON files
3. Update `src/components/Team.astro` to use an `<img>` tag instead of the initial avatar

### 5. OG Image
Add an `og-image.jpg` to `public/` (1200x630px recommended) for social media link previews.

### 6. Update Domain
In `src/pages/index.astro`, update the `og:url` meta tag from `https://dtrhair.co.uk` to your actual domain.

## Deployment

### Netlify (Recommended)
Connect your GitHub repo to Netlify:
- Build command: `npm run build`
- Publish directory: `dist`

### Vercel
```bash
npx vercel
```

## Colour Customisation

All design tokens are CSS variables in `src/styles/global.css`:

| Variable | Value | Usage |
|---|---|---|
| `--accent` | `#C9A96E` | Gold highlight colour |
| `--bg` | `#0D0D0D` | Page background |
| `--surface` | `#141414` | Card/section backgrounds |
| `--text-primary` | `#F0EDE8` | Main text (warm white) |
| `--text-secondary` | `#888888` | Muted/secondary text |
