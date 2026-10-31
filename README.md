# Daystack website

The standalone public website for Daystack, published with GitHub Pages.

- Repository: https://github.com/avick-saha/daystack-website
- Privacy policy: https://avick-saha.github.io/daystack-website/privacy/

The site is plain HTML with local Barlow fonts. It has no build step, JavaScript, analytics, or external dependencies. The font license is in `privacy/assets/Barlow-OFL.txt`.

## Publishing

GitHub Pages publishes the root of the `main` branch. Push a commit to update the site:

```sh
git add index.html privacy README.md .gitignore .gitattributes .nojekyll
git commit -m "Update website"
git push origin main
```

Run these commands from this repository's directory. This repository has its own Git history and remote, separate from the Android application.

## Local preview

From this directory, run `python -m http.server 8000` (on Windows, use `py -3.11 -m http.server 8000`) and open http://localhost:8000/privacy/.

## Policy source

When working inside the Android workspace, `scripts/prepare_play_assets.py` generates `privacy/index.html` from `app/src/main/assets/privacy-policy.txt` and `scripts/templates/privacy.html`. Make policy and design changes in those source files before regenerating, then commit and push the generated website here. No Android source or signing material is included in this public repository.

## Custom domain

The policy currently references `https://daystack.wakubo.in/privacy`. Connecting that address requires configuring a custom domain in this repository's Pages settings and the domain's DNS. Until that is configured, use the GitHub Pages URL above.

See [GitHub's custom domain documentation](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site).
