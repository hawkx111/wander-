# Wander

Landing page for **Wander**: see who's walking nearby right now, tap to join, and just talk.

## Run it

It's a single static file with no build step. Open `index.html` in a browser, or serve the folder:

```sh
python3 -m http.server 8000
```

## Waitlist signups

Near the bottom of `index.html`, set `WAITLIST_ENDPOINT` to any backend that accepts a JSON `POST` with an `email` field (Formspree, Buttondown, your own API, etc.). While it's empty, the form validates emails and saves signups to the visitor's `localStorage`, which is only useful as a demo.
