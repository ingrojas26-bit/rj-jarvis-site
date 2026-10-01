# RJ Jarvis official website

Static, responsive site for RJ Jarvis. No backend, build step, third-party script, analytics or runtime dependency. Pages: Home (`/`), Features (`/features/`), Privacy Policy (`/privacy/`), Terms of Service (`/terms/`) and Support (`/support/`). The legal and support links are visible in every footer.

## Before publishing

1. The support email is **ing.ricardo.rojas26@gmail.com** in Support, Privacy Policy and Terms of Service. Verify that this inbox can receive messages before publication.
2. Read the policy and terms against the actual software configuration and have the operator review them. Do not claim an unconfigured integration is live. Update the effective date if you materially change either document.
3. Publish **only the contents of `website/`** in a separate public repository. Do not upload the parent RJ Jarvis project, `.env`, `work/`, `outputs/`, logs, SQLite databases or OAuth token files.

## Publish free with GitHub Pages

The simplest setup for TikTok URL-prefix verification is a GitHub Pages **user site**, because the website and verification file can live at the URL root:

1. Sign in to GitHub. Create a **public** repository named exactly `USERNAME.github.io`, replacing `USERNAME` with your GitHub username. If that repository already exists, use the project-site option below or a domain you control.
2. Upload the **contents** of `website/` to the repository root, preserving the `features/`, `privacy/`, `terms/`, `support/` and `assets/` directories. The root must contain `index.html` and `.nojekyll`. Do not upload the outer `website` folder as one nested folder.
3. In the repository, open **Settings → Pages → Build and deployment**. Select **Deploy from a branch**, choose the default branch (commonly `main`), choose **`/(root)`**, and save. GitHub's current Pages settings permit publication from a branch root or `/docs`; they do not offer `website/` as a branch source. [GitHub Pages source documentation](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site).
4. Wait for Pages to report the site URL. Open each page in a private browser window and check navigation, footer links, favicon and mobile layout. For a user site the expected addresses are:

   - **Web/Desktop URL:** `https://USERNAME.github.io/`
   - **Privacy Policy URL:** `https://USERNAME.github.io/privacy/`
   - **Terms of Service URL:** `https://USERNAME.github.io/terms/`
   - **Support URL:** `https://USERNAME.github.io/support/`

   Copy the actual URL from GitHub Pages settings; do not submit a placeholder URL to TikTok.

### If you use a normal project repository instead

Create a public repository such as `rj-jarvis-site` and upload the contents of `website/` to its root. Select `main` + `/(root)` under Pages. Its expected URL is `https://USERNAME.github.io/rj-jarvis-site/`; the policy and terms URLs append `privacy/` and `terms/` to that full base. All site links are relative, so they work under this repository prefix. GitHub documents the project-site URL structure in its [custom domain guide](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/about-custom-domains-and-github-pages).

## TikTok verification file later

TikTok for Developers may require verification of the Web/Desktop, Privacy Policy and Terms URLs. For URL-prefix verification, its portal supplies a signature file. **Do not invent the file or its contents.** Download the exact file TikTok supplies, place it at the exact path TikTok specifies within the published site, upload it to the Pages repository, and confirm its public HTTPS URL opens the exact file before clicking Verify. If TikTok requires the file at a domain root that your project-site path cannot provide, use a user site or a domain you control. [TikTok URL verification guidance](https://developers.tiktok.com/docs/en/getting-started-create-an-app).

The website alone does not guarantee app approval. TikTok's app review also asks for accurate product/scope explanations and a demonstration of the actual integration. The site must remain public and the legal links must stay directly visible and active. [TikTok App Review Guidelines](https://developers.tiktok.com/docs/en/app-review-guidelines).

## Local preview

From the parent project directory, run `\.venv\Scripts\python.exe -m http.server 8000 --directory website`, then open `http://127.0.0.1:8000/`. Check `/features/`, `/privacy/`, `/terms/` and `/support/`. Stop the preview with Ctrl+C. This is only a local preview; it does not publish the site.
