---
name: Bot availability
description: The user's requirement that updates must not leave the Telegram casino bot inactive.
---

Keep the Telegram bot running during updates. Do not restart it without the user's approval if the restart could interrupt service.

**Why:** the user explicitly said updates must not make the bot inactive.

**How to apply:** make and test changes without stopping the live workflow. Before activation, explain that this polling bot needs a restart to load code changes and ask for approval; do not claim an update is live until it has been safely activated.
