# Let Me Ask Claude For You

> *For all those people who find it easier to bug you with a question than to just ask Claude themselves.*

A passive-aggressive yet lovable link generator — in the spirit of [letmegooglethat.com](https://letmegooglethat.com/), but for Claude.

## How it works

1. You type a question into the homepage
2. You get a shareable link
3. The recipient sees an animated demo of the question being typed into Claude, then gets redirected to `claude.ai` with the question pre-filled

Everything is 100% static. No backend, no server, no database. Just two HTML files.

## Deploy to GitHub Pages

1. Fork or clone this repo
2. Go to **Settings → Pages**
3. Set source to `main` branch, `/ (root)` folder
4. Your site will be live at `https://<your-username>.github.io/<repo-name>/`

That's it.

## Files

```
index.html   ← Homepage: enter a question, generate a link
ask.html     ← Animated page shown to the link recipient
```

## URL structure

Links look like:

```
https://yoursite.github.io/ask.html?q=What+is+the+meaning+of+life%3F
```

The `q` param contains the URL-encoded question. On load, `ask.html` reads it, plays the typewriter animation, then redirects to:

```
https://claude.ai/new?q=<encoded question>
```

## Customization

- Change the domain/branding in `index.html` (the `eyebrow` span and footer)
- Adjust typewriter speed in `ask.html` (`delay` variable in `typeChar()`)
- The auto-redirect timeout is 1800ms — change it in `ask.html` near the bottom

## License

MIT. Use it however you want.
