# Wander

Landing page for **Wander**: see who's walking nearby right now, tap to join, and just talk.

## Run it

It's a single static file with no build step. Open `index.html` in a browser, or serve the folder:

```sh
python3 -m http.server 8000
```

## Waitlist signups

Signups are sent to Formspree (`WAITLIST_ENDPOINT` near the bottom of `index.html`) and show up in the Formspree dashboard. Signing up takes two steps:

1. The visitor enters their email. It's sent right away as its own submission (subject "New Wander waitlist signup"), so the signup is kept even if they leave.
2. A short follow-up asks two optional questions. If they answer, a second submission (subject "Wander waitlist: follow-up answers") is sent with the same `email` plus:
   - `neighbourhood` (free text)
   - `women_only_mode` (`Yes`, `No` or `Maybe`)

Unanswered questions are left out, and skipping the follow-up sends nothing more. To use a different backend, point `WAITLIST_ENDPOINT` at any service that accepts a JSON `POST` with those fields. If it's left empty, signups are saved only in the visitor's own browser.

## Link previews

`og-image.png` (1200×630) is the image WhatsApp, Reddit and other apps show when the link is shared. The Open Graph tags in `index.html` point at `https://trywander.org/`, so update them if the domain changes.

## Hosting on GitHub Pages

`index.html` sits at the repo root, so Pages can serve it with no build step:

1. Open **Settings → Pages** in this repo.
2. Under **Build and deployment**, set **Source** to **Deploy from a branch**.
3. Pick branch **main** and folder **/ (root)**, then click **Save**.

After a minute or two the site is live. The `CNAME` file serves it at https://trywander.org/.
