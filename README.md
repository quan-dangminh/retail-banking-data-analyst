# Retail Banking — Data Analyst Onboarding Guide

A single-page onboarding guide for Data Analysts in Retail Banking (Vietnamese-language content). It is a static HTML page hosted on Firebase Hosting.

Live project: `e-learning-bi` (Firebase)

## Project structure

```
retail-banking/
├── public/
│   └── index.html          # The guide. This is the only file Firebase serves.
├── firebase.json           # Hosting config: serves public/, SPA rewrite to index.html
├── .firebaserc             # Default Firebase project: e-learning-bi
├── .github/workflows/
│   ├── firebase-hosting-merge.yml         # Deploys to the live channel on push to main
│   └── firebase-hosting-pull-request.yml  # Deploys a preview channel for each pull request
├── .gitignore
└── README.md
```

## Editing the guide

Edit `public/index.html` directly. The page is self-contained: styles are inline and there are no build steps or external assets.

## Deploying

Prerequisites: Node.js and the Firebase CLI (`npm i -g firebase-tools`), and an account with access to the `e-learning-bi` project.

```sh
firebase login
firebase deploy --only hosting
```

Pull requests and merges to `main` deploy automatically through GitHub Actions. Those workflows need the repository secret `FIREBASE_SERVICE_ACCOUNT_E_LEARNING_BI`.

## Notes

- `firebase.json` ignores dotfiles and `node_modules`, so only `public/` is published.
- The `**` rewrite to `/index.html` is harmless for a single page and can be removed if more pages are added.
