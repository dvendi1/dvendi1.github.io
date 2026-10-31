# Portfolio site

A one-page portfolio in plain HTML and CSS. No build step, no frameworks: edit the files and upload them.

```
index.html          all the content
styles.css          all the styling (colors are at the top, under :root)
.nojekyll           tells GitHub Pages to serve the files as they are
assets/
  fonts/            Archivo typeface, self-hosted (SIL Open Font License)
  projects/         photos and videos for each project, one folder per project
  resume.pdf        your resume; the resume links point here
```

## Edit your content

Everything you need to change is in `index.html`. Each section starts with a comment like `<!-- PROJECTS -->`.

- **Hero and title block:** your one-sentence summary, discipline, current role, research focus, location and status. Update "Last revised" whenever you make a big change; the red triangle is a drawing revision mark, so bump the letter (A, B, C...) too.
- **Research interests:** one `<article class="interest">` per topic. Each has a short name, the question you're working on, and a paragraph.
- **Projects:** copy a whole `<li class="project">...</li>` block to add one. Give it an `id` if a research interest links to it.
- **Experience and education:** newest first.
- **Contact:** your email appears twice (the link and the text), so change both if it changes.
- **Resume:** replace `assets/resume.pdf` with a new file of the same name when you update it.
- **Search and tab title:** the `<title>` and `<meta name="description">` at the top of `index.html`.

To preview locally, open `index.html` in a browser. If the font doesn't load that way, run `python3 -m http.server` in this folder and go to http://localhost:8000.

## Publish on GitHub Pages

Your site will live at `https://<your-username>.github.io`.

### Option A: in the browser, no git needed

1. Sign in to GitHub. Click **+** in the top right, then **New repository**.
2. Name it exactly `<your-username>.github.io` (if your username is `octocat`, the name is `octocat.github.io`). Set it to **Public** and click **Create repository**.
3. On the new repository's page, click **uploading an existing file**.
4. Drag in everything from this folder: `index.html`, `styles.css`, `README.md`, `.nojekyll` and the `assets` folder. Click **Commit changes**.
   On a Mac, `.nojekyll` is hidden in Finder. Press Cmd+Shift+. to show it. The site still works without it.
5. Go to **Settings**, then **Pages** in the sidebar. Under **Build and deployment**, set **Source** to **Deploy from a branch**, choose the **main** branch and the **/ (root)** folder, and click **Save**.
6. Wait a few minutes, then visit `https://<your-username>.github.io`. The first publish can take up to 10 minutes.

To update the site later, open a file on GitHub and click the pencil icon to edit it, or upload a new version of the file.

### Option B: with git

```bash
cd path/to/this/folder
git init
git add .
git commit -m "First version of portfolio"
git branch -M main
git remote add origin https://github.com/<your-username>/<your-username>.github.io.git
git push -u origin main
```

Then do step 5 above to turn on Pages.

### Using your own domain (optional)

If you buy a domain such as `dylanvenditti.com`, add it under **Settings > Pages > Custom domain** and follow GitHub's DNS instructions there.
