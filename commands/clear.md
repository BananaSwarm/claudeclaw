---
description: Clear session and start fresh
---

Clear the current Claude session by backing it up and restarting the daemon with a fresh session.

First, resolve the ClaudeClaw plugin install path by reading `~/.claude/plugins/installed_plugins.json` — find the entry under `plugins` with a key containing `claudeclaw` and use its `installPath` value.

Then run:
```bash
bun run "<installPath>/src/index.ts" --clear
```

Replace `<installPath>` with the actual resolved path.

This will:
1. Rename `session.json` → `session_<index>.backup` (preserving the old session)
2. Stop the running daemon if any
3. The next `/heartbeat:start` will create a brand new session

Report the output to the user.
