# Sunsetrock Studio — legal (public)

Public legal pages for App Store Connect across John's apps. App source repos stay private; this one is public and hosted via GitHub Pages at the custom domain `sunsetrockstudio.com` (see `CNAME`).

- Site root: https://www.sunsetrockstudio.com/
- Folia Privacy Policy: https://www.sunsetrockstudio.com/legal/folia/privacy-policy/
- Folia Terms of Service: https://www.sunsetrockstudio.com/legal/folia/terms-of-service/
- FLUX Courier Privacy Policy: https://www.sunsetrockstudio.com/legal/flux/privacy-policy/

**DNS (Squarespace):** `www` must CNAME to `jvivenzio814.github.io`. The bare domain (`sunsetrockstudio.com`) currently has Google `ghs` A records, which 301 to www and **drop the path** — that is why `/legal/folia/privacy-policy/` looked broken. Either keep using `www`, or replace those apex A records with GitHub Pages (`185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`).

Do **not** use the FLUX URL for Folia (or vice versa) in App Store Connect. `/privacy-policy.html` is a chooser, not a single-app policy.

Each app gets its own folder under `legal/<app-name>/`. Add new apps' legal pages the same way. Use **https**, not http.
