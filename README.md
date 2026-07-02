# Beckham Lab website

A static site built with [Jekyll](https://jekyllrb.com) and hosted free on
GitHub Pages. Content lives in plain text/YAML files — no HTML editing needed for
day-to-day updates.

---

## 1. Put it online (GitHub Pages)

You have two options depending on the repository name.

### Option A — user site (simplest URL: `kshbeckham.github.io`)
1. Create a new GitHub repository named **`<your-username>.github.io`**.
2. Upload everything in this folder (or `git push` it) to the `main` branch.
3. In the repo: **Settings → Pages → Build and deployment → Source = Deploy from a branch**, branch `main`, folder `/ (root)`.
4. Wait ~1 minute. Your site is live at `https://<your-username>.github.io`.
5. Leave `baseurl: ""` in `_config.yml` (already set).

### Option B — project site (URL: `<username>.github.io/lab-site`)
1. Create a repo with any name, e.g. **`lab-site`**, and push this folder to it.
2. Turn on Pages as in step 3 above.
3. In `_config.yml`, set `baseurl: "/lab-site"` (match the repo name exactly).

### Custom domain (optional)
If you have a domain (e.g. `beckhamlab.org`), add it under **Settings → Pages → Custom domain**,
create a `CNAME` file containing the domain, set `url:` in `_config.yml`, and keep `baseurl: ""`.

---

## 2. Preview locally (optional but recommended)

You need Ruby installed. Then, from this folder:

```bash
bundle install          # one time
bundle exec jekyll serve # then open http://localhost:4000
```

The site rebuilds automatically as you edit.

---

## 3. Editing content

Everything you'll change routinely is in `_config.yml`, `_data/`, and `_posts/`.

| To change… | Edit… |
|---|---|
| Lab name, tagline, email, address, social links | `_config.yml` |
| The top navigation | `_data/navigation.yml` |
| Group members | `_data/people.yml` |
| Publications | `_data/publications.yml` |
| Funders & awards | `_data/funding.yml` |
| News posts | add a file to `_posts/` |
| Research page wording | `research.md` |

### Adding a news post
Create a file in `_posts/` named `YYYY-MM-DD-a-short-slug.md`:

```markdown
---
layout: post
title: "New paper out in Nature Microbiology!"
date: 2026-08-01
# image: my-photo.jpg   # optional; put the file in assets/images/
---

Write the post here in plain text. Links like <https://doi.org/...> work automatically.
```

It appears at the top of the News page and on the home feed automatically.

### Adding a person
Copy a block in `_data/people.yml` into the right group (`pi`, `postdocs`, `phd`, `masters`),
fill in name / role / bio, and (optionally) add a headshot to `assets/images/` and point
`photo:` at the filename. Delete the `[Student name]` placeholders once you have real members.

### Adding photos / logos
Drop image files into `assets/images/`, then reference them by filename
(`photo: kate.jpg`, `logo: royal-society.png`, or `image: away-day.jpg` in a post).

---

## 4. What's where

```
_config.yml            site-wide settings
_data/                 navigation, people, publications, funding (edit these)
_posts/                news items (one file each)
_layouts/              page shells (default, post)
_includes/             nav, footer, head, reusable snippets
assets/css/style.css   all styling
assets/images/         your photos and logos
index.html             home page
research / people / publications / funding / news   the pages
```

---

## 5. A note on the placeholders

The publications, the PI bio, funders and awards are pulled from the public Newcastle
staff profile and are real. The **team members** (postdoc / PhD / MSc) and the **news posts**
are examples — swap them for your own. The email is `kate.beckham@ncl.ac.uk`.
