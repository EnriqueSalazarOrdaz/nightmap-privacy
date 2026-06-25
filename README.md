# nightmap-privacy

Static, single-page Privacy Policy for the **NightMap** Android app (`com.nightmap.app`), built to be hosted on **GitHub Pages**. The resulting public URL can be used in:

- Google AdMob → **Privacy & messaging**
- Google Play Console → **App content → Privacy policy**

## Files

| File         | Purpose                                              |
| ------------ | ---------------------------------------------------- |
| `index.html` | The privacy policy page (responsive HTML/CSS, no build step). |
| `README.md`  | This file.                                           |

## Publishing with GitHub Pages

1. Create a **public** repository named `nightmap-privacy` on GitHub.
2. Commit and push `index.html` (and this `README.md`) to the `main` branch:
   ```bash
   git add index.html README.md
   git commit -m "Add NightMap privacy policy"
   git push origin main
   ```
3. In the repository on GitHub, go to **Settings → Pages**.
4. Under **Build and deployment**:
   - **Source:** Deploy from a branch
   - **Branch:** `main`  /  Folder: `/ (root)`
   - Click **Save**.
5. Wait about 1–2 minutes for the first deployment. GitHub Pages will publish the site at:
   ```
   https://<your-github-username>.github.io/nightmap-privacy/
   ```
6. Open that URL to confirm the page loads, then paste it into AdMob and the Play Console.

> Tip: GitHub serves `index.html` automatically, so the root URL above is your privacy policy link. No extra path is needed.

## Updating the policy

- Edit `index.html` and update the **Last updated** date near the top of the page.
- Commit and push to `main`; GitHub Pages redeploys automatically within a couple of minutes.

## Before you publish — things to replace

- **Contact email:** The page uses `enrique.salazar.dev@gmail.com`. Replace it (in both the visible text and the `mailto:` link in `index.html`) if your contact address changes.
- **Last updated date:** Currently set to **June 25, 2026**. Update it whenever you change the policy.

## Notes on content

This policy intentionally does **not** claim that the app collects no data, because Google AdMob and Google Play may collect advertising identifiers, device data, and diagnostics under their own privacy policies. It covers AdMob banner and rewarded ads, the Google UMP consent flow, the `nightmap_pro_monthly` Pro subscription via Google Play Billing, credits, advertising identifiers, children's privacy, data retention, and user choices.

This template is provided to help you get a policy online. It is not legal advice. Review it against your actual data practices and applicable laws before publishing.
