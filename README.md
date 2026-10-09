# Khanpanion GitHub Pages delivery

Public address: https://khanacademy-backtrack.github.io/

The application source remains in [KhanAcademy-Backtrack-Demo](https://github.com/KhanAcademy-Backtrack/KhanAcademy-Backtrack-Demo).

## Automatic publication

**Publish Khanpanion** checks the application's `main` branch every five minutes.
For a new commit it runs the application tests, type check and production build,
then publishes the generated `out/` directory. Unchanged commits skip rebuilding.
The public `/release.json` records the exact tested application commit.
`deployment.json` here is updated only after that public receipt is verified.

The schedule is automatic, but GitHub can delay runs; this is not an immediate
cross-repository push trigger. Both hosts follow application main independently.
A failed test or build keeps the last successful Pages release online. Newer main
changes supersede an older build before deployment, and runs are serialized.

## Retry or rollback

Use **Actions → Publish Khanpanion → Run workflow** to check main immediately.
Leave **force** off to skip an already-published revision; enable it to rebuild
that same revision. For a rollback, revert the application commit on main and
let the next check publish the tested result.

GitHub may disable scheduled workflows after 60 days without repository activity.
Successful releases commit the deployment receipt, keeping an actively updated
repository active. After a long idle period, re-enable the workflow in Actions if
needed. The last deployed site remains available while a schedule is disabled.

No personal access token, SSH deployment key, paid service or additional account is
required. This repository disallows deploy keys. Only GitHub's short-lived workflow
tokens are used, with write access confined to deployment and receipt jobs; the
application build has read-only permissions. External Actions are pinned to commits.

## Learner data and access

Progress is stored locally for each website address. Existing progress on
`khanpanion.vercel.app` does not automatically appear on this address. Khan videos
and other resources depend on the venue allowing those services. Automatic
publication does not fix a blocked hostname or change the existing slide QR.
