# codesapien.dev

Static brand site for CodeSapien. Serves the landing page and privacy policy
required for Google Play Console developer verification and the Play Store
listing's Data Safety form.

## Files

- `index.html` — landing page (brand + apps + contact)
- `privacy.html` — privacy policy, mapped to Play Console Data Safety form fields
- `CNAME` — tells GitHub Pages to serve at the custom domain
- `favicon.png` *(optional, drop here later)*

## Hosting: GitHub Pages

This repo is set up for static hosting via GitHub Pages. To deploy:

1. **Push to GitHub** as a public repo.
2. **Repo Settings → Pages**:
   - Source: *Deploy from a branch*
   - Branch: `main` / folder `/(root)`
3. GitHub builds and serves at `https://<username>.github.io/<repo>/` within ~30s.
4. **Custom domain**: in the same Pages settings, enter `codesapien.dev` and save.
5. **DNS at your registrar**:
   ```
   @   A   185.199.108.153
   @   A   185.199.109.153
   @   A   185.199.110.153
   @   A   185.199.111.153
   www CNAME <username>.github.io
   ```
6. After DNS propagates (~15 min for `.dev`), check **"Enforce HTTPS"** in
   the Pages settings. GitHub auto-provisions a Let's Encrypt cert.

## Verifying

```bash
curl -I https://codesapien.dev/        # expect HTTP/2 200
curl -I https://codesapien.dev/privacy.html
```

## Updating

Every commit to `main` redeploys automatically. To edit:

```bash
# edit index.html or privacy.html
git add -A
git commit -m "site: update privacy policy"
git push
```

## License

The HTML and CSS in this repo are MIT-licensed. The CodeSapien name, logo,
and brand are © CodeSapien (Lance Walker).
