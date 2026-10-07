# Thaali — photo nutrition

Snap a photo of a meal or drink, or describe it in words, and see calories, protein, carbs, fat, fibre and minerals for each item.

The app is a single `index.html` file. It calls an AI vision model directly from the browser, using an API key that each user adds under **AI settings**. The key is stored only in that browser's local storage.

## Get an AI key

- **Google Gemini (free tier):** https://aistudio.google.com/apikey
- **Anthropic Claude (paid):** https://console.anthropic.com/settings/keys

## Put it on GitHub Pages

1. Create a new public repository on GitHub, for example `thaali`.
2. Click **Add file → Upload files**, upload `index.html` (and this README), then **Commit changes**.
3. Go to **Settings → Pages**. Under **Source**, choose **Deploy from a branch**, select `main` and `/ (root)`, then **Save**.
4. After a minute or two the site is live at `https://<your-username>.github.io/thaali/`.
5. Open the site, click **AI settings** (top right), paste your key and save.

## Important

- **Never put your API key inside `index.html` or anywhere in the repository.** Anyone can read files in a public repo and use your key.
- Each person who uses the site adds their own key. For a public launch where users don't need a key, put a small proxy (for example a Cloudflare Worker) between the app and the AI provider so the key stays on the server.
- The "Today" meal log is saved in the browser only, so it doesn't sync across devices.
- Nutrient values are estimates (IFCT 2017 / USDA reference data). Not medical advice.

## Install on Android

The site is an installable app (PWA). After uploading **all files** in this folder (`index.html`, `manifest.json`, `sw.js` and the four icon PNGs):

1. Open the GitHub Pages link in **Chrome** on the Android phone.
2. Tap **Install app** in the top bar, or Chrome's **⋮ menu → Install app / Add to Home screen**.
3. Thaali appears on the home screen and opens full screen like a normal app.

To publish on the Google Play Store later, enter the site link at https://www.pwabuilder.com and download the Android package (Trusted Web Activity). A Google Play developer account is needed.
