# FlurryTube v1.1 — Google Login + History
Developed by Wilzz.

## A. Upload to GitHub Pages
Replace these files in the repository root: `index.html`, `manifest.webmanifest`, and `sw.js`. Commit to `main` and wait for Pages to deploy.

## B. Set up Google login (required)
1. Open https://console.firebase.google.com/ and create a Firebase project (or use an existing one).
2. In Authentication > Sign-in method, enable **Google**.
3. In Authentication > Settings > Authorized domains, add your GitHub Pages host exactly: `ikomangwisnu12345-design.github.io`.
4. In Project settings > General > Your apps, create a **Web app** and copy its Firebase web config.
5. Open `index.html` in GitHub and find `const firebaseConfig`. Replace the four `PASTE_...` values with your Firebase web config values (`apiKey`, `authDomain`, `projectId`, `appId`).
6. In Firestore Database, create a database. Open Rules and publish the contents of `firestore.rules` included in this ZIP.

Firebase web config is intended to be used in a browser. Never put a service-account JSON, private key, or server credential in this website. Do not share passwords or OAuth tokens.

## What works
- Google sign-in/sign-out once Firebase is configured.
- Profile name, email, and Google profile picture.
- Search history stored locally; when signed in and Firestore is configured, history syncs to that Google user's private Firestore path.
- Clear history, working navigation tabs, dark/light theme, touch-swipe tab navigation, and glass-style UI.

## Current limits
- Search still opens YouTube results in a new page/location; this does not yet show YouTube's video feed inside FlurryTube.
- Saved tab is a placeholder until a video catalog/player is added.
- History records searches made from FlurryTube; it cannot read a user's YouTube watch history.
- Google login is not active until you complete the Firebase setup above.
