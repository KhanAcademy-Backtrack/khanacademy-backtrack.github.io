# Khanpanion GitHub Pages delivery

Public address: https://khanacademy-backtrack.github.io/

This repository publishes the existing Khanpanion application on GitHub Pages. The application source remains in [KhanAcademy-Backtrack-Demo](https://github.com/KhanAcademy-Backtrack/KhanAcademy-Backtrack-Demo).

Every push to the application repository's `main` runs its **Publish GitHub Pages** workflow: install pinned dependencies, test, typecheck and build. After those checks pass, an isolated publication job copies only the generated static export into this repository's `site/` directory. This repository's **Publish Khanpanion** workflow then deploys `site/` to the existing public address.

## Automatic releases and recovery

Push or merge reviewed changes to `main` in the application repository. No separate manual publication is needed. Do not edit generated files under `site/` here. Both hosts follow application `main`, with independent deployment times.

To retry a failed build/publication, use **Actions → Publish GitHub Pages → Run workflow** on `main` in the application repository. To retry only final Pages deployment of the tested files, use **Actions → Publish Khanpanion → Run workflow** here. To roll back source, revert the change on application `main`; the normal checks run again. A failed test or build leaves the last successful site online.

Actions are pinned to commit hashes. The application's `github-pages-publishing` environment permits only `main` and stores `PAGES_DEPLOY_KEY`. Its public key has write access only to this publishing repository; build jobs do not receive it. The standard `GITHUB_TOKEN` alone cannot push into this separate repository or trigger the downstream workflow. No paid service or personal access token is used.

The deployed `/release.json` records the application commit. Confirm both workflows succeed and that this receipt matches the intended revision. Access still depends on the venue's DNS and filtering; automatic deployment does not fix a blocked hostname.

## Learner data

Progress is stored locally for each website address. Existing progress on `khanpanion.vercel.app` does not automatically appear on this address. Khan videos and other external resources still depend on the venue allowing those services.
