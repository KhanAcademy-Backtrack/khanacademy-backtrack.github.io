# Khanpanion competition site

Public address: https://khanacademy-backtrack.github.io/

This repository publishes the existing Khanpanion application on GitHub Pages for the school competition. The application source remains in [KhanAcademy-Backtrack-Demo](https://github.com/KhanAcademy-Backtrack/KhanAcademy-Backtrack-Demo).

The initial release uses source commit `fc9b3d93f0accb80793415bf8d19b0e806a93f8a`, including the Courses, CET Reviewers, Practice Exams and Daily Recall home shortcuts. The workflow runs the source tests and production build, then publishes only its `out` directory. GitHub Actions are pinned to commit hashes. No paid domain, additional account or deployment secret is required.

## Publish another reviewed release

Open **Actions → Publish Khanpanion → Run workflow** and provide the full reviewed source commit SHA. Leaving the input blank republishes the pinned competition release. The original Vercel site continues to follow the application repository's `main` branch independently.

The deployed `/release.json` records the application commit. Check the Actions deployment result and test the public link on the venue's Wi-Fi before distributing a new release.

## Learner data

Progress is stored locally for each website address. Existing progress on `khanpanion.vercel.app` does not automatically appear on this address. Khan videos and other external resources still depend on the venue allowing those services.
