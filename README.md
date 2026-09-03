
# ChargeFlow Website

Marketing site for **ChargeFlow Technologies Inc.** — wireless EV charging embedded beneath drive-thru lanes and parking stalls. No cable, no app: the vehicle charges automatically the moment it's positioned over an embedded coil.

A live pilot is currently in development in Ottawa, Ontario.

## About the project

ChargeFlow uses inductive wireless power transfer (the same principle as Qi phone charging, scaled for outdoor/pavement use) to charge EVs during dwell time that would otherwise return zero charge — drive-thru queues, parking stalls, restaurant lots, hotel parking, and fleet depots.

This site covers:

- **How it works** — the four-step park / detect / charge / go cycle
- **Applications** — drive-thru lanes, parking lots, restaurants, hotels, fleet depots
- **Technology** — operating frequency, SAE J2954 alignment, coil and power-electronics specs
- **For property owners** — the revenue model for hosting a ChargeFlow installation
- **Video** — a short walkthrough of the drive-thru and parking-lot systems
- **Contact** — how to get in touch about a pilot

## Tech stack

Plain HTML, CSS, and vanilla JavaScript — no build step, no framework, no dependencies to install. Fonts (Space Grotesk, Inter, IBM Plex Mono) are loaded from Google Fonts via `<link>` tags.

## File structure

```
.
├── index.html   # the entire site — markup, styles, and script in one file
├── poster.jpg   # poster frame shown before the video is played
└── ChargeFlow_Ad_Video.mp4   # the embedded product video
```

`index.html` references `poster.jpg` and `ChargeFlow_Ad_Video.mp4` by relative path, so **all three files must stay in the same folder** — if you move or rename one, update the `<video>` tag's `src` and `poster` attributes in `index.html` to match.

## Running locally

No build step needed. Either:

- Open `index.html` directly in a browser, or
- Serve the folder locally so the video loads over `http://` instead of `file://`:

  ```bash
  python3 -m http.server 8000
  ```

  then visit `http://localhost:8000`.

## Deploying with GitHub Pages

1. Push this repo to GitHub with all three files at the root (or inside a `/docs` folder — see below).
2. In the repo, go to **Settings → Pages**.
3. Under **Build and deployment**, set **Source** to "Deploy from a branch."
4. Choose the branch (usually `main`) and the folder (`/root` or `/docs`), then save.
5. GitHub publishes the site at `https://<your-username>.github.io/<repo-name>/` within a few minutes.

Note: `ChargeFlow_Ad_Video.mp4` is a few MB. GitHub Pages serves it fine, but if you outgrow GitHub's file-size/bandwidth limits later, consider hosting the video on a CDN or video platform and pointing the `<source>` tag at that URL instead.

## Before you publish

A couple of placeholders need your real details:

- **Contact email** — `index.html` currently links to `hello@chargeflow.tech` in the footer. Replace it with your real inbox.
- **Contact form** — "Request a pilot" currently opens a `mailto:` link. If you want an actual submission form, wire it up to a form backend (e.g. Formspree, a Google Form, or your own endpoint) and update the footer markup.

## License

Add a license of your choice (e.g. MIT) if you want this repo to be reusable by others. None is included by default.
