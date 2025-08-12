# Task 6 – GitHub Pages Questions

### 1️⃣ What happens when you delete the repo?
If you delete a repository that has GitHub Pages enabled:

- The website associated with it becomes immediately unavailable.
- The content is permanently removed from GitHub (unless you have a backup).
- Any custom domain linked to it will no longer serve your site.

### 2️⃣ What is the default file that loads?
By default, GitHub Pages serves `index.html` (or `index.md`) from the repository’s root, `/docs` folder, or branch configured for Pages.

If no `index` file is found, it may show a 404 error.

### 3️⃣ Can you use a custom domain?
Yes, you can use a custom domain with GitHub Pages:

- Configure it in the repository settings under `Pages` → `Custom domain`.
- Add a `CNAME` file in your repo with your domain name.
- Update your DNS provider to point to GitHub Pages IP addresses.
