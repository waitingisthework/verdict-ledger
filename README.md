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

## Methodology versions

`METHODOLOGY.md` is the version-controlled copy of the
[methodology page](https://waitingisthework.com/methodology/). Its first line is
the version and date (`v1.0 · 2026-10-27`); every change gets a dated entry in
`CHANGELOG.md` and a commit. Each released version is timestamped the same way
as the verdict files: `stamps/METHODOLOGY-v<X.Y>.sha256` holds the SHA-256 of
`METHODOLOGY.md` as released, and `stamps/METHODOLOGY-v<X.Y>.ots` the
OpenTimestamps proof anchoring it in Bitcoin.

A version is only released when the header carries a higher version number than
the last stamped one and `CHANGELOG.md` has an entry for it with a date and what
changed. Older versions are never deleted: they stay in the git history, each
under its own stamp.

```
ots verify stamps/METHODOLOGY-v1.0.ots -f METHODOLOGY.md
```

(Verify against the file as it stood in the commit that was stamped, e.g.
`git show a22924f:METHODOLOGY.md`, once a later version has replaced it.)
