# KIMOX — Personal Portfolio (HTML / CSS / JavaScript / Bootstrap)

A standalone portfolio for Edrine Kimuli / KIMOX. **This version intentionally replaces Next.js/TypeScript** with HTML5, CSS3, vanilla JavaScript, Bootstrap 5 and Bootstrap Icons. No Node.js, React, TypeScript, Tailwind or build process is required.

## 1. Quick start

Extract the ZIP. Open the folder `kimox-static` in VS Code. Install the **Live Server** extension (Ritwick Dey), right-click `index.html` and choose **Open with Live Server**. Alternatively, from this folder run:

```bash
python -m http.server 8000
```

Then visit `http://localhost:8000`. Python is optional if using Live Server. Opening `index.html` directly also works for the core display, though a local server is recommended.

**All essential Bootstrap CSS, Bootstrap JS, and Bootstrap Icons are bundled locally in `vendor/`**, so even without internet access, navigation, social icons, and the project slider render. Google Fonts are optional external resources; the site has system-font fallbacks.

## 2. Folder guide

- `index.html` — full homepage and all primary visible sections
- `css/style.css` — original dark/glassmorphism responsive design, animations and reduced-motion support
- `js/data.js` — **edit personal information, all social media links, skills, projects, images, CV and contact endpoint here**
- `js/main.js` — dynamic content, project slider, project cards, filters, mobile menu, scroll reveals, form handling
- `projects/*.html` — five actual project detail pages driven by `js/data.js`
- `assets/images/portrait.svg` — explicit portrait placeholder
- `assets/images/<project-slug>.svg` — five distinct project screenshot placeholders
- `assets/icons/kimox-mark.svg` — logo/favicon
- `assets/documents/` — put your CV PDF here
- `vendor/` — locally bundled Bootstrap 5 and Bootstrap Icons
- `404.html` — custom not-found page
- `robots.txt` — search robot guidance; add sitemap after choosing your domain

## 3. Replace images

Replace `assets/images/portrait.svg` with your photograph (for example `portrait.jpg`). Then change `portrait:'assets/images/portrait.svg'` in `js/data.js` to `portrait:'assets/images/portrait.jpg'`.

For a project, place your screenshot into `assets/images/`, then update that project's `image` field in `js/data.js` to the new path. **You do not need to edit project pages to replace images.** The design uses responsive `object-fit:cover`; landscape screenshots close to 3:2 look best. Use compressed JPG/WebP/PNG and descriptive alternative text as applicable.

## 4. Social platforms

`js/data.js` contains GitHub, YouTube, Instagram and X public profile links using the handles you supplied. They show actual platform-specific Bootstrap Icons. The WhatsApp entry is deliberately hidden until you confirm and add a fully international `https://wa.me/...` number. If a social URL is blank, its icon is automatically hidden. Add a LinkedIn object to `socials` once you have that URL.

## 5. Contact form: real delivery setup

The form includes required fields, native browser validation, a honeypot and clear status messaging. **It cannot deliver email until you configure a service**. Create a Formspree form at `https://formspree.io`, verify the email that receives submissions, and paste its real endpoint into `formEndpoint` in `js/data.js`.

Example:

```js
formEndpoint: 'https://formspree.io/f/YOUR_REAL_FORM_ID'
```

Do NOT paste a fake ID. The submission sends `FormData` using `fetch()`; success is shown only after a 2xx response. Formspree handles delivery and server-side spam restrictions according to your account. Do not put private API tokens in client-side JavaScript.

## 6. CV download

Put your real PDF in `assets/documents/`, for instance `edrine-kimuli-cv.pdf`, and set:

```js
cv:'assets/documents/edrine-kimuli-cv.pdf'
```

The CV button is disabled until this is done.

## 7. Edit projects and skills

In `js/data.js`, update project descriptions, status, technology list, problem, approach, screenshot path and verified repository/live demo links. To add a sixth project, add a project object and duplicate an existing page in `projects/`, changing only its `data-slug`. Never add false statistics or project outcomes. Update skill group arrays as your knowledge evolves.

## 8. Customization

CSS tokens are defined at the beginning of `css/style.css`. Primary brand colors are orange `#F58220`, near-black `#1C1C1C`, white, and light grey. The current layout uses subtle translucent glass cards, layered geometric backgrounds, responsive CSS Grid, a manual project slider, scroll reveals and restrained hover effects. It respects OS **reduced motion** settings.

## 9. Hosting / deployment

No build is needed. Upload the **contents** of `kimox-static` to any static host: GitHub Pages, Netlify, Cloudflare Pages, or an ordinary web host. On GitHub Pages, use Settings → Pages → Deploy from a branch and choose the root folder; links are relative so the project works on a subpath. For Netlify, use the folder as the publish directory and leave the build command empty.

After you get a domain, create `sitemap.xml` with URLs from your own domain and add it to `robots.txt`. Add canonical metadata to the HTML pages. Do not use a fake domain.

## 10. Testing checklist

Run from a local server and check desktop/mobile layouts; verify the navbar, filters, slider arrows, 5 project pages, social links, CV disabled state and the contact form's unconfigured message. Use keyboard Tab/Enter and system reduced motion preferences. Test the Formspree integration only after you configure it.

## Important caveats

- Portrait and screenshot assets are illustrative SVG placeholders, **not real photographs**.
- Form delivery, CV, WhatsApp, unknown project statuses, and repository URLs need your real data.
- Empty testimonials, certifications and blog posts are not shown, rather than inventing content.
- Bootstrap 5.1.1 and Bootstrap Icons are included locally under their respective open-source licenses. They can be upgraded by replacing the files in `vendor/` with a matching release.
