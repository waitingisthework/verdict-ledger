# Waiting Is the Work: verdict ledger

Every verdict published on [waitingisthework.com](https://waitingisthework.com/track-record/),
frozen the first time it appears and never rewritten.

## Why this exists

The track-record page recomputes past verdicts with the current scoring function,
over a rolling 12-month window. That is the right way to measure the method, and
the wrong way to prove what was actually said. This ledger is the record of what
was said, and when.

## Files

- `verdicts.csv`: one row per (ticker, day). `date` is the evaluation date,
  `recorded` is the day the row entered this ledger. Rows are only ever added.
- `revisions.csv`: days where the site now shows a different verdict than the
  one frozen here, because a scoring change reached back in time. The ledger
  keeps the original; the difference is listed, not hidden.
- `stamps/<day>.verdicts.csv`, `.sha256`, `.ots`: the exact file as it stood
  that day, its SHA-256, and an [OpenTimestamps](https://opentimestamps.org)
  proof anchoring that hash in the Bitcoin blockchain.

## What is proven and what is not

A git commit date is set by whoever makes the commit, so it proves nothing on
its own. The `.ots` proof does: it shows the file existed no later than the
Bitcoin block it points to, and it can be checked without trusting this
repository, GitHub or the author.

```
pip install opentimestamps-client
ots verify stamps/2026-09-28.ots -f stamps/2026-09-28.verdicts.csv
```

The ledger started on 2026-09-28. Rows with an earlier `date` were first
stamped that day: for them the proof covers "no later than 2026-09-28", not the
evaluation date itself. From then on the gap between `date` and the stamp is at
most a few days.

A stamp shows when something was written, not that it was right. Whether the
verdicts were any good is what the track-record page measures.
