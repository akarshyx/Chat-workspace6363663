---
name: Filtered pnpm installs around firewall blocks
description: Replit package-firewall failures in a workspace can sometimes be avoided by installing only the app and its dependencies.
---

When a monorepo install is blocked on a transitive dependency that is outside the app being brought up, try a workspace-filtered install for the app and its dependency closure before changing upstream dependency versions.

**Why:** A broad install in this repository hit a Replit package-firewall block on an older server-only package, while the filtered install of the frontend app and its local dependencies completed without changing the lockfile.

**How to apply:** For a nested pnpm workspace, run the filtered install from the nearest workspace root; widen the install only if the target app needs the blocked package.
