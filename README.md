# Academic website

A static, responsive academic website for GitHub Pages. No build tools or dependencies are required.

## Pages

- `index.html` — short introduction and contact details
- `research.html` — research interests and ongoing projects
- `publications.html` — publications, conference posters and presentations, and work in progress
- `teaching.html` — lists of courses taught and teaching assistantships
- `cv.html` — CV download area
- `assets/css/style.css` — shared styles

Replace “Your Name”, institutional details, and placeholder entries with your own content. Each page contains the same navigation and footer so it works without JavaScript. When changing navigation or shared identity details, update all five HTML files. The current page is identified with `aria-current="page"`.

## Add your profile photo

Upload your portrait as `assets/images/profile.jpg` (create the `images` directory under `assets` if needed). In `index.html`, replace the `photo-placeholder` div with the image element provided in the comment above it, and update its alt text with your name. The frame crops the photo to a portrait format; adjust `object-position` in the stylesheet if needed.

## Add your CV

GitHub Pages hosts static files; it does not accept uploads from website visitors.

1. Upload your PDF to this repository as `assets/documents/cv.pdf` (on GitHub, open `assets/documents` and choose **Add file → Upload files**).
2. In `cv.html`, replace the “CV coming soon” heading and message with your preferred wording.
3. Uncomment the supplied PDF link immediately below that message.
4. Commit the PDF and HTML changes to the publishing branch. You can replace the PDF at the same path for future updates.

## Local development

From the repository root, run:

```sh
python3 -m http.server 8000 --bind 127.0.0.1
```

Check each page and the top navigation in a browser. There is no build step or automated test suite.

## GitHub Pages

Commit and push these files to `main`. In the repository's **Settings → Pages**, use **Deploy from a branch**, select `main` and `/ (root)`, and save. Once GitHub finishes deploying, the site will be available at https://mid-lewis.github.io/.

The `.nojekyll` file tells GitHub Pages to serve this plain HTML/CSS site without Jekyll theme processing. Keep it in the repository root.

All page and stylesheet links are relative, and no external fonts or scripts are required. Each page's stylesheet URL includes a `?v=` version token so browsers fetch updated styles after a release. Whenever the stylesheet changes, update that token consistently in all five HTML pages (the current token uses the first 12 characters of the CSS file's SHA-256 hash).

To check a deployment, open the repository's **Actions** tab and confirm that the latest Pages run succeeded for your commit. If a previously opened tab still shows an old version, reload it after deployment completes.
