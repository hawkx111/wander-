# Wander

Landing page for **Wander**: see who's walking nearby right now, tap to join, and just talk.

## Run it

It's a single static file with no build step. Open `index.html` in a browser, or serve the folder:

```sh
python3 -m http.server 8000
```

## Waitlist signups

Signups are sent to Formspree (`WAITLIST_ENDPOINT` near the bottom of `index.html`) and show up in the Formspree dashboard. To use a different backend, point `WAITLIST_ENDPOINT` at any service that accepts a JSON `POST` with an `email` field. If it's left empty, signups are saved only in the visitor's own browser.

## Hosting on GitHub Pages

`index.html` sits at the repo root, so Pages can serve it with no build step:

1. Open **Settings → Pages** in this repo.
2. Under **Build and deployment**, set **Source** to **Deploy from a branch**.
3. Pick branch **main** and folder **/ (root)**, then click **Save**.

After a minute or two the site is live at https://hawkx111.github.io/wander-/.
