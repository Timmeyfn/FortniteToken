# Pirate Chest — GitHub Pages

## 1. Put it on GitHub Pages
1. Sign in at github.com and click **New repository**. Name it `pirate-chest`, make it **Public**, and click **Create repository**.
2. Click **uploading an existing file**, drag in `index.html` and the whole `img` folder, then click **Commit changes**.
3. Go to **Settings → Pages**. Under *Build and deployment*, choose **Deploy from a branch**, then **main** and **/ (root)**, and click **Save**.
4. Wait about a minute. Your site is at `https://YOUR-USERNAME.github.io/pirate-chest/`.

To have the site at `https://YOUR-USERNAME.github.io/` instead, name the repository `YOUR-USERNAME.github.io`.

## 2. Turn on the shared leaderboard (free Firebase)
GitHub Pages only hosts files, so the leaderboard needs somewhere to store scores.
1. Go to console.firebase.google.com, click **Create a project**, and name it `pirate-chest` (you can skip Analytics).
2. In the left menu, click **Build → Realtime Database → Create Database**, pick a location, and start in **locked mode**.
3. Open the **Rules** tab, replace everything with the contents of `firebase-rules.json`, and click **Publish**.
4. Copy the database URL shown on the **Data** tab. It looks like `https://pirate-chest-default-rtdb.firebaseio.com`.
5. In `index.html`, find `const FIREBASE_URL = '';` and paste the URL between the quotes. Commit the change on GitHub.

Until you do this, the site works fine but the leaderboard only shows your own score.

## Notes
- Each visitor's anonymous ID, inventory and token count are saved in their own browser.
- Because a static site rolls chests in the browser, a determined person could fake a token. The database rules limit this: a player can only gain +2 tokens at a time, at most once a minute, and names must look like "Anonymous #1234".
- The Pirate Token video plays from YouTube (`Lpu_0baQJs4`). To change it, edit `YT_ID` in `index.html`.
