# Trainer icon PRs

SVG changes on master send a `stratagem-icons-updated` repository_dispatch event to
Stratagem-Hero-Trainer. You can also run the notification workflow manually.

## Setup

Install the Trainer workflow first. Add the source repository Actions secret
`TRAINER_DISPATCH_TOKEN`: a fine-grained PAT restricted to Stratagem-Hero-Trainer with
Contents read/write, which GitHub requires for repository_dispatch. Set an expiration and
rotate it before expiry. Never commit the token.

The Trainer reads source master and opens a PR containing only new SVGs, in the matching
department/Warbond folders. Ask Codex to complete the existing Trainer catalogue in that
PR, then review and merge it manually. No code lookup or LLM call runs in GitHub Actions.

An open icon PR is left untouched. Further icons wait for the next daily/manual sync after
it is merged or closed. Existing icons and game data are never overwritten or deleted.
See the Trainer's [setup guide](https://github.com/nvigneux/Stratagem-Hero-Trainer/blob/master/docs/stratagem-sync.md).
