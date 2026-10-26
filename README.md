# Md Khalid Syfullah — personal website

A simple white academic website for GitHub Pages. GitHub builds it automatically: you only edit text files, in the browser if you like, and the site updates in about a minute. No install is needed.

## 1. Put it online (one time)

1. On GitHub, create a new **public** repository named exactly **`Khalidsyfullah.github.io`**.
2. Open the repository, click **Add file → Upload files**, drag in **everything inside this folder** (not the folder itself), and click **Commit changes**.
3. Go to **Settings → Pages**. Under *Build and deployment*, set **Source: Deploy from a branch**, **Branch: `main`**, folder **`/ (root)`**, and click **Save**.
4. After 1–2 minutes your site is live at **https://khalidsyfullah.github.io**.

To change your photo later, upload a new one as `assets/img/profile.jpg` (square works best).

## 2. Where to edit what

| To change… | Edit this file |
|---|---|
| **Monthly updates** (home page) | `_data/updates.yml` |
| Name, title lines, emails, profile buttons, menu | `_config.yml` |
| About-me text on the home page | `index.md` |
| Publications | `_data/publications.yml` |
| Projects | `_data/projects.yml` |
| Trips and travel photos | `_data/travel.yml` (photos go in `assets/img/travel/`) |
| Research, Teaching, Achievements, Resume | `research.md`, `teaching.md`, `achievements.md`, `resume.md` (plain text) |
| Accent colour | `assets/css/style.css`, the `--accent` line at the top |

To edit on GitHub: open the file → click the **pencil icon** → make changes → **Commit changes**.

## 3. Adding a monthly update

Open `_data/updates.yml` and paste a new block at the **top** of the list, under the comment section:

```yaml
- month: November 2026
  items:
    - "Presented our paper at **IEEE SMC 2026** in Vienna."
    - "Gave a talk at [SIU Research Day](https://example.com)."
```

- Newest month goes first.
- Put each item in "double quotes".
- `**bold**` and `[link text](https://...)` work inside items.
- Use **spaces, not tabs**. Keep the same indentation as the existing blocks.

The home page shows the latest 8 months (change `home_update_months` in `_config.yml`). The **All Updates** page always shows everything.

## 4. Adding a paper

Open `_data/publications.yml` and paste at the top:

```yaml
- title: "My New Paper Title"
  authors: "**Md Khalid Syfullah**, Co Author"
  venue: "IEEE Conference Name"
  year: 2027
  status: accepted          # optional
  link: https://doi.org/... # optional
  code: https://github.com/... # optional
  section: conference       # or: journal
```

## 5. Adding a new page

1. Create a file such as `talks.md` with this at the top:

   ```
   ---
   layout: default
   title: Talks
   permalink: /talks/
   ---

   Write your content here in Markdown.
   ```

2. Add it to the menu in `_config.yml` under `navigation`:

   ```yaml
     - title: Talks
       url: /talks/
   ```

## If something breaks

A build error is almost always a YAML typo: a missing quote, a tab, or wrong indentation. Check the **Actions** tab on GitHub: a red ✗ shows the file and line. Fix that line and commit again; the old version of the site stays online until the fix works.

## Preview on your own computer (optional)

Install Ruby, then run `bundle install` and `bundle exec jekyll serve` in this folder, and open http://localhost:4000.
