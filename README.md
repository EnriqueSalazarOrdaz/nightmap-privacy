# NightMap Privacy Policy

Privacy policy and support contact for NightMap on Android, iPhone, and iPad.

- Official site and privacy policy: https://nightmap-58a4d.web.app/
- Firebase privacy links for existing releases: https://nightmap-58a4d.web.app/privacy/ and https://nightmap-58a4d.web.app/privacy/nightmap-privacy/
- Legacy GitHub Pages link: https://enriquesalazarordaz.github.io/nightmap-privacy/
- AdMob seller file: https://nightmap-58a4d.web.app/app-ads.txt

## Publish updates

Edit the root `index.html` and update the date shown in the policy. Copy it to the Firebase homepage, then deploy from this repository:

```sh
cp index.html hosting/public/index.html
firebase deploy --only hosting --project nightmap-58a4d --account enriquesa7@gmail.com
```

`firebase.json` deploys `hosting/public` to the `nightmap-58a4d` Hosting site. Keep `app-ads.txt`, `404.html`, and both existing privacy routes in that directory. To update an existing privacy page, copy the revised policy to that route's `index.html` before deploying.

GitHub Pages publishes the root `index.html` from `main` for older app releases. Push the updated source to `main` when you want to update that copy.
