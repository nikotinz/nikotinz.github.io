# nikotinz.github.io

Personal website, built with [Quarto](https://quarto.org/) and served by GitHub Pages from the `docs/` folder.

## Layout

```
index.qmd            home page (bio + 5 most recent talks/posts)
talks/               one folder per talk or poster
blog/                one folder per post
software.qmd         packages and apps
teaching.qmd         group meeting R sessions, workshops, olympiads
publications.qmd     selected papers
theme.scss           fonts and colours
_quarto.yml          navbar, footer, site settings
docs/                rendered site (do not edit by hand)
```

## Add a talk or poster

1. Copy an existing folder in `talks/`, e.g. `talks/2025-09-rss-mams/`, and rename it `YYYY-MM-short-name`.
2. Edit the header of `index.qmd`:

   ```yaml
   title: "Title of the talk"
   description: "One sentence for listings and link previews."
   date: "2026-03-15"
   event: "Name of the event, city"   # shown in the Talks table
   categories: [talk, MAMS]
   ```

3. Put the slides link, PDF or code link in the `::: links` block. A PDF can sit in the same folder and be linked by its file name.
4. Run `quarto render` (or the Render button in RStudio) and push.

The talk appears on the Talks page and, if it is among the five newest items, on the home page.

## Add a blog post

Same as above, in `blog/`. If the post is a write-up of a talk, give it an `event:` line in the header and it will also appear on the Talks page. Posts can contain R chunks. Their results are stored in `_freeze/`, so a post is only re-run when you change it. Commit `_freeze/` along with `docs/`.

## Publish

```
quarto render
git add -A
git commit -m "New talk"
git push
```

In the repository settings on GitHub, Pages should be set to deploy from the `main` branch, `/docs` folder.
