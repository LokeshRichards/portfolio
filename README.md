# Lokesh Richards — portfolio

Hand-coded static site. No build step: everything in `public/` is served as-is by Cloudflare.

## Structure

```
public/
  index.html    # the whole site (HTML, CSS, JS inline)
  404.html      # not-found page
  favicon.svg
  robots.txt
  _headers      # security + cache headers
wrangler.jsonc  # Cloudflare config
```

## Edit

Open `public/index.html`. Placeholders to fill are marked with square brackets, e.g. `[YOUR EMAIL]`,
`[Add a result: ...]`, `[Screenshot: ...]`.

Screenshots: add images to `public/images/` and replace each `<div class="case-shot">…</div>` with
`<img class="case-shot" src="/images/name.webp" alt="…" width="1200" height="800" loading="lazy">`.

## Preview locally

```
npx wrangler dev
```

## Deploy (one-time setup)

1. Cloudflare dashboard → **Workers & Pages** → **Create** → **Import a repository**.
2. Pick this GitHub repo. Build command: leave empty. Deploy command: `npx wrangler deploy`.
3. Save. Every push to `main` now deploys automatically.
4. Optional: **Settings → Domains & Routes → Add custom domain**.
