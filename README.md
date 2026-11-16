# x-algo-watch

Every 10 minutes a GitHub Action checks the latest commit on `xai-org/x-algorithm` main. When it changes, it POSTs to my Grok Bot routine's webhook so the bot runs a full repocheck, then records the new SHA in `last_sha.txt`.

Secrets (Settings > Secrets and variables > Actions): `WAKE_URL` (routine webhook URL) and `WAKE_KEY` (its sender key). Nothing secret is stored in the repo.

If the ping fails, the SHA isn't recorded, so the next run retries.
