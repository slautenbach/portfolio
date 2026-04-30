# Sam Lautenbach — Portfolio

Static portfolio site built with plain HTML, CSS, and JavaScript. Hosted on GitHub Pages.

## File structure

```
.
├── index.html              # Landing page (hero, about, sections, contact)
├── education.html          # Section 01
├── engineering.html        # Section 02
├── ai-engineering.html     # Section 03 (under construction)
├── data-science.html       # Section 04
├── css/style.css           # All styles
├── js/main.js              # Mobile nav, scroll reveals, active link
├── images/                 # Drop project images here
├── documents/              # Drop resume.pdf and other docs here
├── .nojekyll               # Tells GitHub Pages to skip Jekyll processing
└── README.md
```

## How to publish on GitHub Pages

1. Create a new GitHub repository. If you want the site at `https://<username>.github.io`,
   name the repo exactly `<username>.github.io`. Otherwise any repo name works and the
   site will live at `https://<username>.github.io/<repo>/`.
2. Initialize git in this folder and push:
   ```bash
   git init
   git add .
   git commit -m "Initial portfolio"
   git branch -M main
   git remote add origin https://github.com/<username>/<repo>.git
   git push -u origin main
   ```
3. On GitHub: Settings → Pages → Build and deployment → Source: **Deploy from a branch** →
   Branch: **main**, folder: **/ (root)**. Save.
4. Wait ~1 minute. The URL will appear at the top of the Pages settings.

## How to add content

### Replace placeholders
Open each HTML file and search for `[ image:` or `Project Title` — those are the spots
that need real content. Each project card has:

- `project__tag` — short label (e.g., "Web app · React")
- `project__title` — name
- `project__desc` — 1–2 sentences
- `project__links` — links to demos, repos, write-ups

### Add images
1. Save image to `images/` (e.g., `images/project1.jpg`).
2. Replace the placeholder block in the HTML:
   ```html
   <div class="project__thumb">
     <img src="images/project1.jpg" alt="Description of image" />
   </div>
   ```

### Add the resume
Save your PDF as `documents/resume.pdf`. The "Download resume" button on the home page
and contact section already point there.

### Add more project cards
Copy any `<article class="project reveal"> ... </article>` block and paste it inside the
`<div class="projects">` of the relevant section page.

## Customization

- **Colors**: edit the `:root` variables at the top of `css/style.css`. The single accent
  color (currently `#2563eb`) is used for the dot in the logo, hover states on the
  primary button, and the section number on each sub-page.
- **Name / tagline**: edit `index.html` — the hero title and lead paragraph.
- **About section**: edit the two paragraphs in `.about__body`.
- **Contact links**: replace placeholder GitHub and LinkedIn URLs.
- **Fonts**: Inter (sans) + JetBrains Mono (numbers/labels). Both loaded from Google Fonts.

## Local preview

Just open `index.html` in a browser. For a live-reload server:
```bash
python -m http.server 8000
# then visit http://localhost:8000
```
