# streak-keeper

Automated streak keeper for [@eliaseffects](https://github.com/eliaseffects).

## How it works

Runs nightly via Hermes cron (21:00 + 23:45 local). The script
[`keep-streak.py`](~/.hermes/scripts/keep-streak.py) queries the GitHub API
for any commit authored today (UTC day) by `contact@eliasstevenson.com` — the
verified email linked to the account, which is the only one that counts toward
the contribution graph.

- **Already committed today** → script stays silent, nothing happens.
- **No commit today** → appends a line to `activity.log`, commits with
  `contact@eliasstevenson.com` identity, and pushes. Streak survives.

## Why public

Public repo commits always render on the contribution graph. Private repo
commits only count if "Private contributions" is enabled in profile settings.

## Files

- `activity.log` — append-only log of automated commits.
