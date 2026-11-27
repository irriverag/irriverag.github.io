# Isn's personal website

Personal site for Isn, a first-year cybersecurity student at Purdue. Hosted on GitHub Pages from the repo `irriverag/irriverag.github.io`, live at https://irriverag.github.io.

## Stack and structure

- Plain HTML, CSS and a small vanilla JS script, all in **one file: `index.html`**. No framework, no build step, no package manager. Keep it that way unless asked.
- `hero.jpg` sits next to `index.html` in the repo root. It is the user's own picture. Never delete, rename or replace it.
- Font: Heuristica, self-hosted as woff2 in `fonts/` (regular, italic, bold; SIL OFL licence in `fonts/OFL.txt`), falling back to Georgia/serif. No Google Fonts.
- Deploys automatically: anything pushed to `main` goes live on GitHub Pages within a minute or so.

## Layout (current, intentional)

Loosely modelled on dbmaindex.org's layout, but kept light and minimal.

- **Top-left header:** `hero.jpg` small (52px, 44px on mobile) with the name "Isn" to its right. The whole thing links to `#about`.
- **Left column:** a vertical nav, in this order: About, Projects, Thoughts. Under it, GitHub (github.com/irriverag) and LinkedIn (linkedin.com/in/ianriverag) icons. The site opens on About. There is no Home or Contact tab any more; old `#home` and `#contact` links fall back to About.
- **Right column:** the content of the selected tab.
- **Theme button:** after the LinkedIn icon. It shows the mode it switches *to*: a moon in light mode, a sun in dark mode. The first visit follows the system setting; after a click, the choice is saved in `localStorage` (key `theme`). A small script in `<head>` sets `data-theme` on `<html>` before the page draws, so there's no white flash. Dark colours are the `:root[data-theme="dark"]` variables at the top of the CSS.
- **Phone width (below 820px):** the nav becomes one row with the icons (GitHub, LinkedIn, theme) on the right, slightly smaller. It fits on one row down to 375px wide; narrower phones wrap the icons onto a line under the nav.

## How the tabs work

Each tab is a `<section class="panel" id="panel-NAME">`. The nav links use hashes (`#about`, `#projects`, and so on), and the `show()` script at the bottom of the file shows the matching panel and gives that nav link the blue `active` color. To add a tab, add a nav `<li>` with `href="#name"` and a matching `<section class="panel" id="panel-name">`.

Entries inside a tab use `#tab/slug`: add an `<li>` to the tab's `<ul class="entries">` and an `<article class="entry" id="entry-TAB-SLUG">` in the same panel. `show()` hides the list and shows that article.

## Content status

- **About:** the About text and a "Latest update" line below it (`[YYYY-MM-DD] what changed`). Update that line by hand whenever the site changes. About interests are networking, beginner scripting, the gym, Overwatch, reading and Pokémon cards.
- **Projects:** a list of entries in the form `[Fall 2026] Title`. Each one opens its own page (`#projects/SLUG`) with a ← back link, a meta line, and a body box that stops at 50vh and fades out at the bottom. Entries: Lab Network Switcher and Scheduled Backups (two Bash coursework scripts, split from the old "Bash Automation Scripts" entry; Scheduled Backups has a "Problems I ran into" section). Their "View on GitHub" links stay commented out until the instructor OKs posting the code. Next planned: a Packet Tracer networking lab.
- **Thoughts:** (formerly Reading) blog-style list (`<ul class="entries posts">`: date, title, a line under each), with posts opening at `#thoughts/slug` like projects. No posts yet, so it shows the placeholder ("also under construction!!") and a commented-out template.

## Decisions to respect

- **No email address anywhere on the site.** The user removed it on purpose to avoid scraping.
- **No Purdue Hackers webring.** The user is not a member. Don't add it back.
- **No Spotify embed.** The user removed it on purpose. Don't add it back.
- **Keep the style minimal:** white background (or `#161616` in dark mode), Heuristica serif font, the `#4a5bd4` accent (`#8c9bf2` in dark mode). The user doesn't want a terminal or hacker look.
- **Writing tone:** casual and natural, in first person as Isn. The user found stiff, list-heavy copy awkward.

## Checking changes

Open `index.html` directly in a browser, or run `python3 -m http.server` in this folder and visit http://localhost:8000. Check that:

- every tab opens
- the picture and name stay in the top left and link to About
- the layout works at phone width (below 820px)
- both themes look right, and the theme button swaps moon/sun
