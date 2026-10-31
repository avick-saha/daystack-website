# Daystack website

The standalone public website for Daystack, published with GitHub Pages.

- Repository: https://github.com/avick-saha/daystack-website
- Privacy policy: https://daystack.wakubo.in/privacy/

The site is plain HTML with local Barlow fonts. It has no build step, JavaScript, analytics, or external dependencies. The font license is in `privacy/assets/Barlow-OFL.txt`.

## Publishing

GitHub Pages publishes the root of the `main` branch. Push a commit to update the site:

```sh
git add index.html privacy CNAME README.md .gitignore .gitattributes .nojekyll
git commit -m "Update website"
git push origin main
```

Run these commands from this repository's directory. This repository has its own Git history and remote, separate from the Android application.

## Local preview

From this directory, run `python -m http.server 8000` (on Windows, use `py -3.11 -m http.server 8000`) and open http://localhost:8000/privacy/.

## Policy source

When working inside the Android workspace, `scripts/prepare_play_assets.py` generates `privacy/index.html` from `app/src/main/assets/privacy-policy.txt` and `scripts/templates/privacy.html`. Make policy and design changes in those source files before regenerating, then commit and push the generated website here. No Android source or signing material is included in this public repository.

## Custom domain

GitHub Pages uses `daystack.wakubo.in` as the custom domain, also recorded in the root `CNAME` file. The domain's DNS must contain this record in the `wakubo.in` zone:

| Type | Name | Target | TTL |
| --- | --- | --- | --- |
| CNAME | `daystack` | `avick-saha.github.io` | Default |

The target is only the hostname, without `https://` or a repository path. Once DNS resolves, GitHub can provision the domain's HTTPS certificate. Verify the certificate and enable **Enforce HTTPS** in the repository's Pages settings when available. The custom URL will not work until DNS and certificate provisioning finish.

See [GitHub's custom domain documentation](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site).
