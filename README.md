# GoalPay Tracker

Savings goals, work hours needed (per day, week, fortnight, month) and expense tracking.
One codebase in `www/` becomes a website, a Windows .exe and an Android app.
Accounts use Firebase email + password with required email verification.

## Setup
1. **Firebase:** console.firebase.google.com > create project.
   - Build > Authentication > Get started > enable **Email/Password**.
   - Build > Firestore Database > Create database, then Rules tab: paste `firestore.rules`, Publish.
   - Project settings > Your apps > Web (</>) > copy the config into `www/firebase-config.js`.
   - Authentication > Settings > Authorized domains: add `YOUR-USERNAME.github.io`.
2. **GitHub:** create a repo, upload everything in this folder (keep the `.github` folder), push to `main`.
   - Settings > Pages > Source: **GitHub Actions**.
3. Open the **Actions** tab. After a few minutes you get:
   - the website at `https://YOUR-USERNAME.github.io/REPO-NAME/`
   - `GoalPay-Windows-exe` and `GoalPay-Android-apk` under the finished run's Artifacts.

## Updating
Change anything in `www/`, commit and push. The workflow rebuilds the website, .exe and .apk, so a change on your PC reaches mobile too. Accounts and data are shared through Firebase.

## Run on your PC
`npm install` then `npm start`.

## Notes
- The APK is a debug build: on your phone allow "install unknown apps" to install it. Publishing to Google Play needs a signed release build.
- A Mac or iPhone app needs a Mac to build; ask if you want it.
