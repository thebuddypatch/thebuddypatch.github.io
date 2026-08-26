# The Buddy Website

Static site — no build step, no dependencies.

## Files

```
index.html        Thai homepage (default)
index-en.html     English homepage
faq.html          Thai FAQ page
faq-en.html       English FAQ page
assets/           images (logo, product boxes, reviews, photos)
```

## Deploy to GitHub Pages

1. Create a new repository on GitHub (e.g. `the-buddy-website`). Public is required for free Pages.
2. Upload every file in this folder to the repository root — `index.html` must sit at the top level, not inside a subfolder. Keep the `assets/` folder next to it with its name unchanged.
   - Web UI: **Add file → Upload files**, drag the whole contents in, then **Commit changes**.
   - Command line:
     ```
     git init
     git add .
     git commit -m "Initial site"
     git branch -M main
     git remote add origin https://github.com/<user>/<repo>.git
     git push -u origin main
     ```
3. In the repository, go to **Settings → Pages**.
4. Under **Source** choose **Deploy from a branch**; set branch to `main` and folder to `/ (root)`. Save.
5. Wait 1–2 minutes. The site goes live at `https://<user>.github.io/<repo>/`.

## Notes

- The `.nojekyll` file is included so GitHub serves the folders as-is.
- All internal links are relative, so the site works from a subfolder URL without changes.
- The FAQ buttons point to the existing external FAQ site. To use the bundled FAQ pages instead, replace `https://thebuddypatch.github.io/the-buddy-patch-faq/` with `faq.html` (and `faq-en.html` in the English page).
- Custom domain: add it under **Settings → Pages → Custom domain**, then point a CNAME record at `<user>.github.io` with your DNS provider.
