# nectar frontend

A single-page, tmux-style landing site. Everything is in `index.html`, with no build step and no dependencies.

The page has four panes:

| pane | what it does |
| --- | --- |
| `0: whoami` | logo and tagline |
| `1: nav directory` | `ls -la` of the site; click a row or use ↑ ↓ / j k |
| `2: pwd` | renders the selected section's README, glow-style |
| `3: mail` | email capture with an SMTP-style send transcript |

## Run locally

Open `index.html` in a browser, or serve the folder:

```sh
python3 -m http.server 8000
```

## Deploy

Any static host works. On Vercel, import this repo with the framework preset **Other** and no build command.

## Configure

At the top of the main `<script>` in `index.html`:

- `TO`: the contact address. **It's a placeholder (`root@nectar.example`) until the real domain is set.** The domain also appears in the page text. Search for `nectar.example`.
- `DEMO_URL`: link for the `demo` entry. Leave it empty to show "deploying".
- `SEND_ENDPOINT`: a URL that accepts `POST {from, subject, message}` and returns 2xx only after the email is actually sent. Leave it empty and the form falls back to the visitor's mail app. It never claims an email was sent when it wasn't.

## Variants

`variants/` keeps earlier logo and color explorations:

- `honey-original`: first logo on the warm brown honey palette
- `sharp-drip-logo`: hand-drawn italic logo with dripping honey
- `code-rain-logo`: logo that forms out of slow code rain
