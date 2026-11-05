# Trainer synchronization notifications

`.github/workflows/notify-trainer.yml` sends `stratagem-icons-updated` via
`repository_dispatch` when SVG paths change on master. It also supports manual dispatch.
Keep creating and organizing icons as usual; no data file or code sequence is required here.

Set the source repository Actions secret `TRAINER_DISPATCH_TOKEN` to a fine-grained token
restricted to `nvigneux/Stratagem-Hero-Trainer` with Contents read/write (the GitHub API's
required permission for dispatch). Do not commit the token. Set an expiration and rotate it.

The Trainer workflow must be installed on its default branch first. It always reads this
repository's actual master snapshot, never an untrusted payload ref/path. Trainer's own
manual trigger and daily fallback recover from failed notifications. Adds, modifications,
renames and missing files are identified there; removed SVGs do not delete Trainer entries.

Installation, bot credentials, manual code verification, branch protection and maintenance
are documented in the Trainer's
[docs/stratagem-sync.md](https://github.com/nvigneux/Stratagem-Hero-Trainer/blob/master/docs/stratagem-sync.md).
No PR is automatically merged and no new sequence becomes playable without explicit review.
