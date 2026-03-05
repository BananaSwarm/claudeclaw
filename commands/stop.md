---
description: Stop the heartbeat daemon
---

Stop the heartbeat daemon.

First, resolve the ClaudeClaw plugin install path by reading `~/.claude/plugins/installed_plugins.json` — find the entry under `plugins` with a key containing `claudeclaw` and use its `installPath` value.

Then run:
```bash
bun run "<installPath>/src/index.ts" --stop
```

Replace `<installPath>` with the actual resolved path.

Report the output to the user.
