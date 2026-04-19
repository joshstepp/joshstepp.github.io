# joshstepp.com

Personal site for Josh Stepp — cybersecurity professional, USAF veteran, and creator of the IntrusionsInDepth Podcast.

A deliberately simple, single-page static site. No build step, no frameworks, no tracking. Just HTML and CSS.

## Philosophy

> Much of the internet is bloated, filled with ads, and overly complex. I like simple.

This site is the embodiment of that. It's one HTML file with inlined CSS, served as-is.

## Structure

```
.
├── index.html      # The entire site (HTML + inlined CSS)
└── README.md       # This file
```

That's it. No `node_modules`, no `dist/`, no config files.

## Sections

| Section         | Purpose                                                        |
|-----------------|----------------------------------------------------------------|
| Header          | Name, tagline, and terminal-style status tag                   |
| About           | Bio, current role at Elastic, and background                   |
| Blog            | Link to Substack newsletter                                    |
| Podcast         | IntrusionsInDepth links (site, YouTube, Apple, Spotify, X)     |
| Career Advice   | Link to interview on Code & Culture Collective                 |
| Now             | `/now`-page style snapshot of current focus (updated manually) |
| Connect         | Social links and collaboration form                            |
| On this site    | Short note on the minimalist design philosophy                 |
| Footer          | Copyright                                                      |

## Design

- **Font:** Roboto Mono (Google Fonts) — monospace throughout, reinforcing the technical/terminal feel
- **Palette:** Black header, white background, light gray section cards (`#f0f0f0` / `#e9e9e9`), near-black text (`#1a1a1a`), green accent (`#4ade80`) for status indicators
- **Motifs:** Terminal prompts (`>`, `$`), code-comment markers (`//`), and a subtle grid overlay on the header
- **Profile photo:** Grayscale with a contrast bump, pulled from GitHub avatar CDN
- **Layout:** Single column, 860px max-width, responsive down to mobile
- **CSS:** All custom properties live in `:root`, so recoloring is a single-file edit

## Running Locally

Open `index.html` in any browser. Really — double-click it.

For a local server (useful if you want to test with relative paths or share on LAN):

```bash
# Python 3
python -m http.server 8000

# Or with Node
npx serve .
```

Then visit `http://localhost:8000`.

## Updating Content

### The `/now` section

Inspired by [Derek Sivers' /now movement](https://sive.rs/now). Update it whenever current focus shifts:

1. Find the `<section id="now">` block in `index.html`
2. Update the date in `<p class="now-meta">Updated [DATE]</p>`
3. Edit the `<li>` items under `<ul class="now-list">`

### Links

All external links live inside `<section>` blocks and use `target="_blank"`. The podcast section uses `.link-list` styling (pill buttons); social links use `.social-links` styling (slightly larger pills).

### Colors

Change the CSS custom properties at the top of the `<style>` block:

```css
:root {
    --black: #000000;
    --text: #1a1a1a;
    --text-muted: #555555;
    --border: #cccccc;
    --bg: #ffffff;
    --bg-section: #f0f0f0;
    --bg-section-alt: #e9e9e9;
    --accent-green: #4ade80;
}
```

## Deployment

Any static host works. Popular options:

- **GitHub Pages** — push to a repo, enable Pages in settings
- **Netlify** — drag-and-drop the folder, or connect the repo
- **Cloudflare Pages** — connect the repo, no build command needed
- **Plain VPS** — drop `index.html` in your web root

No build command. No environment variables. No runtime.

## Browser Support

Modern evergreen browsers. Uses CSS custom properties, `clamp()`, CSS Grid, and Flexbox — all widely supported since ~2020.

## License

Content (text, bio, branding) © Josh Stepp. All rights reserved.

The underlying HTML/CSS structure is free to borrow for your own personal site — that's the whole point of keeping it simple.

## Contact

- Website: you're on it
- Newsletter: [joshstepp.substack.com](https://joshstepp.substack.com/)
- Podcast: [intrusionsindepth.com](https://www.intrusionsindepth.com/)
- Collaborate: [form](https://forms.gle/XTYYvRiS6KDXfDdk7)
