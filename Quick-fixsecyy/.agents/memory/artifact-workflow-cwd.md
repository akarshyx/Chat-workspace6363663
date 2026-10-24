---
name: Nested artifact workflow working directory
description: Launch commands for artifact-owned services nested inside a repository.
---

Artifact-managed workflow commands start from the artifact directory, not the repository root. Calculate `cd` paths relative to that directory. For bot services with single-instance locks, also check for an orphaned process before restarting.

**Why:** a repository-root-relative command failed when launched from the nested artifact directory, and a stale bot process then blocked the managed restart.

**How to apply:** before starting an artifact-owned service, confirm its working directory and use relative paths from the artifact directory; after a failed restart, inspect process and port state before trying again.
