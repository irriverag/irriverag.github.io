# Isn's personal website

Personal site for Isn, a first-year cybersecurity student at Purdue. Hosted on GitHub Pages from the repo `irriverag/irriverag.github.io`, live at https://irriverag.github.io.

## Stack and structure

- Plain HTML, CSS and a small vanilla JS script, all in **one file: `index.html`**. No framework, no build step, no package manager. Keep it that way unless asked.
- `hero.jpg` sits next to `index.html` in the repo root. It is the user's own picture. Never delete, rename or replace it.
- Font: EB Garamond from Google Fonts, falling back to Georgia/serif.
- Deploys automatically: anything pushed to `main` goes live on GitHub Pages within a minute or so.

## Layout (current, intentional)

- **Left column:** the name "Isn" and a vertical nav, in this order: About, Home, Projects, Thoughts, Contact. The site opens on About by default.
- **Top right corner:** `hero.jpg`, fixed in place, 200px max on desktop (100px on mobile), visible on every tab.
- **Right column:** the content of the selected tab.

## How the tabs work

Each tab is a `<section class="panel" id="panel-NAME">`. The nav links use hashes (`#about`, `#projects`, and so on), and the `show()` script at the bottom of the file shows the matching panel and gives that nav link the blue `active` color. To add a tab, add a nav `<li>` with `href="#name"` and a matching `<section class="panel" id="panel-name">`.

Entries inside a tab use `#tab/slug`: add an `<li>` to the tab's `<ul class="entries">` and an `<article class="entry" id="entry-TAB-SLUG">` in the same panel. `show()` hides the list and shows that article.

## Content status

- **About:** written. Interests are networking, beginner scripting, the gym, Overwatch, reading and Pokémon cards.
- **Projects:** a list of entries in the form `[Fall 2026] Title`. Each one opens its own page (`#projects/SLUG`) with a ← back link, a meta line, and a body box that stops at 50vh and fades out at the bottom. First entry: Bash Automation Scripts (coursework; the "View on GitHub" link stays commented out until the instructor OKs posting the code). Next planned: a Packet Tracer networking lab.
- **Thoughts:** (formerly Reading) placeholder text ("also under construction!!").
- **Contact:** GitHub link only (github.com/irriverag).
- **Home:** an empty panel. Only the picture shows there.

## Decisions to respect

- **No email address anywhere on the site.** The user removed it on purpose to avoid scraping.
- **No Purdue Hackers webring.** The user is not a member. Don't add it back.
- **No Spotify embed.** The user removed it on purpose. Don't add it back.
- **Keep the style minimal:** white background, serif font, the `#4a5bd4` accent. The user doesn't want a terminal or hacker look.
- **Writing tone:** casual and natural, in first person as Isn. The user found stiff, list-heavy copy awkward.

## Checking changes

Open `index.html` directly in a browser, or run `python3 -m http.server` in this folder and visit http://localhost:8000. Check that:

- every tab opens
- the picture stays in the top right
- the layout works at phone width (below 820px)
