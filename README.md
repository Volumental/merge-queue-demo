# merge-queue-demo

Playground for GitHub's merge queue. CI is fake (`sleep`), except for one real
check: no two files in `services/` may use the same `port=`.

PRs `add-billing` and `add-search` both claim port 8100. Each passes on its own,
but the queue tests them together and ejects whichever lands second.
