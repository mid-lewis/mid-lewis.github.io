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

All page and stylesheet links are relative, and no external fonts or scripts are required.
