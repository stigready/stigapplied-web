# stigapplied.com

Marketing site for **StigApplied** — AWS AMIs with CIS Level 1/2 and DISA STIG
remediation applied (the hardened counterpart to [StigReady](https://stigready.com),
the minimal base).

Static site, no build step: plain `index.html` with Tailwind / Lucide / Google Fonts
over CDN. Hosted on **GitHub Pages** with the custom domain `stigapplied.com`.

## Deploy

```bash
# edit index.html / assets, then:
git add -A && git commit -m "..." && git push
```

Pages republishes in ~1 minute.

## One-time setup

1. GitHub → Settings → Pages → Source: deploy from `main` (root).
2. Custom domain: `stigapplied.com` (the `CNAME` file pins it); enable **Enforce HTTPS**.
3. DNS at the registrar:
   - apex `stigapplied.com` → A `185.199.108.153`, `185.199.109.153`,
     `185.199.110.153`, `185.199.111.153` (and AAAA `2606:50c0:800{0..3}::153`).
   - `www.stigapplied.com` → CNAME `stigready.github.io`.

## Structure

```
index.html      # the site (hero, features, benchmarks, profiles, pricing)
assets/logo.*   # shared StigReady/StigApplied logo
CNAME           # stigapplied.com
.nojekyll       # serve as-is (no Jekyll)
robots.txt
```
