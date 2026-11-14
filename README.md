# Sunday · NFL lineup reasoning, static demo

Live: https://claytonvlawson.github.io/nfl-demo/

This repo holds only the built demo (no application source). It is a mirror of
a private repository, republished on every change so a link can be handed to a
prospective client without a hosting account behind it.

- The page is a Vite/React build served from a GitHub Pages project site.
- The API is the same Express app, deployed as a Vercel Node function from the
  private source repo: https://nfl-demo-api.vercel.app/api/health
- Data comes from a committed snapshot (2026 season, week 10), so the demo needs
  no live feeds, no API key, and no model call. Answers are computed by the
  deterministic reasoning engine in the source repo.

Rebuild (from the private source repo):

    PAGES_BASE=/nfl-demo/ VITE_API_BASE=https://nfl-demo-api.vercel.app npm run build
    rsync -a --delete dist/ <this repo>/ && cp index.html 404.html

The 404.html is a copy of index.html so any deep link lands on the app instead
of GitHub's 404 page. `.nojekyll` keeps every file served byte for byte.
