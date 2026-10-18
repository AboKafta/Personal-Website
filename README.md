# Georgy Rached — Electrical Engineering Portfolio

A static portfolio site built with plain HTML, CSS, and JavaScript: a home page, one case-study page per project, a résumé PDF, and a 404 page. There is no framework, build step, or backend, so it runs on any static host, including GitHub Pages.

## Preview it on your computer

Open `index.html` in a browser. To preview it the way a host serves it (recommended, so every link behaves exactly as it will online), open a terminal in this folder and run:

```bash
python -m http.server 8000
```

Then visit `http://localhost:8000`.

## Host it on GitHub Pages

The site goes live at **https://abokafta.github.io** if you use a repository named after your username, which is the recommended setup. That gives the site its own root address, which the 404 page relies on.

### Option A: Upload in the browser (no Git needed)

1. Sign in at [github.com](https://github.com) as **AboKafta**.
2. Click **+** (top right) → **New repository**.
3. Name it exactly **`AboKafta.github.io`**, set it to **Public**, and leave "Add a README" unchecked (this folder already has one). Click **Create repository**.
4. On the new repository's page, click **uploading an existing file**.
5. Unzip `georgy-rached-portfolio.zip`, open the `georgy-rached-portfolio` folder, select **everything inside it** (`index.html`, `404.html`, `styles.css`, `script.js`, `README.md`, and the `assets` and `projects` folders) and drag it onto the upload area.
   - Upload the folder's *contents*, not the folder itself, so `index.html` ends up at the top level of the repository.
   - Dragging folders works in Chrome, Edge, and Firefox. If folders don't upload, use Option B.
6. Scroll down and click **Commit changes**.
7. Go to **Settings → Pages**. Under **Build and deployment**, set **Source** to **Deploy from a branch**, choose **main** and **/ (root)**, and click **Save**.
8. Wait a minute or two, then refresh the Pages settings. The address appears at the top. Open **https://abokafta.github.io**.

### Option B: Push with Git

Install Git from [git-scm.com](https://git-scm.com), create the empty `AboKafta.github.io` repository (steps 1–3 above), then in a terminal:

```bash
cd path/to/georgy-rached-portfolio
git init
git add .
git commit -m "Portfolio site"
git branch -M main
git remote add origin https://github.com/AboKafta/AboKafta.github.io.git
git push -u origin main
```

Then turn on Pages (step 7 above).

### Using a different repository name

If you name the repository something else, like `portfolio`, the site lives at `https://abokafta.github.io/portfolio/`. Every page works there except the 404 page's links, which point to the site root. Use the `AboKafta.github.io` name to avoid that.

### Updating the site later

- **In the browser:** open a file in the repository, click the pencil icon to edit, or use **Add file → Upload files** to replace files with the same names. Commit, and the site updates within a minute or two.
- **With Git:** replace the files in your folder, then run `git add .`, `git commit -m "Update"`, and `git push`.

### Optional: custom domain

In **Settings → Pages → Custom domain**, enter a domain you own and follow GitHub's DNS instructions. Once it works, add `<link rel="canonical">` and absolute `og:url` / `og:image` tags to each page's `<head>` so shared links use the domain.

### Good to know

- **Public files:** everything in the repository is public, including the résumé PDF in `assets/`.
- **`.nojekyll`:** an empty `.nojekyll` file at the top level tells GitHub Pages to serve the files as they are. It's optional for this site, and the browser upload may skip it because it's a hidden file. That's fine.

## What's in the site

- **`index.html` (home):**
  - Zig Ziglar quote and intro with GitHub, LinkedIn, email, and résumé links.
  - Featured builds and more builds, filterable by PCB / Embedded / CAD, each with a status label.
  - Skills linked to the projects and courses that used them.
  - Credentials, education with coursework, experience, and contact.
- **`projects/*.html`:** one case-study page per project.
  - Status, role, team, dates, and tools up top.
  - Numbered sections with an "On this page" index on wide screens.
  - Highlights, revision history, and block diagrams where the write-ups support them.
  - The full write-up and a resources list.
- **Drawings:** each project has a technical illustration. Hover over it, tap it, or press Enter on a project page to crossfade to the real photo or render. The four PCB renders line up exactly with their drawings.
- **Image viewer:** click any documentation figure to open it larger. Arrow keys move between figures, clicking zooms, and Esc closes.
- **`404.html`:** not-found page with inline styles.
- **`assets/`:** logo, favicon, portrait, certificates, résumé PDF, and project images (`assets/projects/<project>/`).
- **`styles.css` and `script.js`:** all styling and behavior.

## Setting your skill levels

Every skill in the Skills section has five stars, all empty for now. To fill them in, open `index.html`, find the skill, and change its `data-level` from `"0"` to a number from 1 to 5 (halves like `"3.5"` work too):

```html
<b>KiCad</b><span class="stars" data-level="4" ...></span>
```

The stars and the screen-reader label update automatically. Each skill also appears once, so search the file for its name (for example `KiCad`) to find it.

## Next up

- [ ] Fill in the skill levels (see above).
- [ ] Add demo videos: Heart PCB, Piano PCB, MP3 Player (prototype and final), and the RP2350 test. These were attachments on the Notion pages but weren't included in the PDF exports.
- [ ] Once the site has a domain, add canonical and `og:url` / `og:image` tags.
- [ ] Add photos of the Room Temperature Monitor board if it gets fabricated.
