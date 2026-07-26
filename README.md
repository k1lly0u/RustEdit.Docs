# RustHQ content repository

The documentation published at **rusthq.com/rustedit** lives here.

## How the site reads this repo

[`index.md`](index.md) is the whole definition of the section. Every markdown
link in it to a `.md` file in this repo becomes a page:

```markdown
- [Getting Started](getting-started.md)
- [Working with Prefabs](guides/prefabs.md)
```

| What the site takes | Where it comes from |
| --- | --- |
| Which pages exist | The links in `index.md` |
| Their order | Top to bottom in `index.md` |
| The page title | The link text |
| The URL | The **file name**, lowercased - `getting-started.md` → `/rustedit/getting-started` |
| The page body | The file, minus its front matter |

Everything else in `index.md` - headings, prose, links to other sites - is
ignored, so it stays a readable table of contents rather than a config file.

> One consequence worth knowing: **every** link to a `.md` file in this repo
> becomes a page. Don't link this README, or a contributing guide, or a
> changelog from `index.md` - name them in plain text instead, or they'll be
> published as documentation.

The URL comes from the file name and **not** the title on purpose: rewording a
heading is a normal edit, and it shouldn't break every link anyone has shared.
Renaming a file does change its URL, so avoid it once a page is published.

## Adding a page

1. Add the `.md` file.
2. Add a line to `index.md` where you want it to appear.
3. Open a pull request.

That's it - there's no site-side step, no ticket, nothing to configure.

## Removing a page

Delete its line from `index.md`. The page comes down on the next sync. (Delete
the file too, unless you're only hiding it for now - see `published` below.)

## Front matter

A page can override what the index decided by starting with a `---` block:

```markdown
---
title: Working with Prefabs
nav_label: Prefabs
published: false
---

# Working with Prefabs
```

| Field | Default | What it does |
| --- | --- | --- |
| `title` | The link text in `index.md` | The page heading and browser title |
| `nav_label` | The title | Shorter label for the navbar dropdown |
| `slug` | The file name | Overrides the URL segment |
| `published` | `true` | `false` keeps the page out of the site entirely |
| `draft` | `false` | The inverse of `published`, if you prefer it that way |

Front matter is optional. Most pages don't need any.

Use `published: false` while a page is still being written - it stays in the
repo and in `index.md`, gets reviewed like anything else, and goes live the
moment someone flips it.

## Writing a page

Ordinary markdown. What the site renders:

- **Headings** (`#` through `######`). Two or more and the page grows a table
  of contents down the side, so use them generously.
- **Tables**, like the ones on this page.
- **Horizontal rules** (`---` on its own line - but not as the very first line,
  where it starts a front-matter block instead).
- Bold, italic, strikethrough, inline `code`, fenced code blocks, block quotes,
  ordered and unordered lists, links.
- **Images** - see below.

Keep the first heading of a page as its title - the site shows the page title
above your content, so starting with `# Something Else` reads oddly.

## Images

Put the file in `images/` and link it relatively:

```markdown
![The prefab browser](images/prefab-browser.jpg)
```

This repo is the image host. On sync a relative image path is rewritten to that
file's raw URL on GitHub, so the picture shows on GitHub *and* on the site, and
it arrives in the same pull request as the words around it. There is no upload
step and no separate asset store.

- Reference images relatively - `images/x.jpg`, or `../images/x.jpg` from a
  subfolder. An absolute URL is left exactly as written, which is right for
  something you don't control but worse for anything that belongs with the page:
  a file in this repo is reviewed with it and can't vanish later.
- Name the file after what it shows: `prefab-browser.jpg`, not `screenshot1.jpg`.
- Keep them small. A screenshot doesn't need to be a megabyte - 1600px wide and
  properly compressed is plenty, and the page renders them 480px tall at most.
- Always write real alt text. It is the caption for anyone who can't see it.

Links between pages work the same way: `[prefabs](prefabs.md)` becomes that
page's URL on the site, as long as the page is listed in `index.md`.

## Publishing

A push to `main` triggers a webhook and the site rebuilds this section: pages
added, changed, reordered, removed, all in one pass. Nothing is published from
any other branch, so work in progress is safe on a branch or in a fork.

If a push doesn't seem to have landed, a site administrator can hit **Sync** on
the category in the admin panel, which does the same thing and reports what
went wrong if the index is malformed.

## Conventions

- One topic per page. Split a page rather than letting it sprawl.
- File names lowercase, words separated by hyphens: `your-first-map.md`.
- Sentence case in headings ("Working with prefabs", not "Working With
  Prefabs") - except proper nouns.
- Link between pages with ordinary relative links: `[prefabs](prefabs.md)`.
- Images live in `images/`, named for what they show.
