# Kendawg's Dashboard

One-page Claude Artifact that shows the output of Ken's scheduled tasks (packages, Homestead weather, Bambu P1S prices, Japan flight prices).

- `index.html` is the whole app. It is published as a Claude Artifact: https://claude.ai/artifact/Kh2AWyz9CafRfhRCCVFhgj
- **Refresh all** fires each scheduled task through the Claude Code Remote connector.
- **Refresh frequency** (hourly, 2x a day, daily, weekly) rewrites the cron schedule on each task.
- Each task writes its result to the artifact database, collection `cards` (ids `packages`, `weather`, `bambu`, `japan`). The card format, including per-row `detail` and `links`, lives in the db document `meta/format`, which the task prompts read each run.

To self-host later, serve `index.html` and replace the `claude.use("db")` and `claude.use("mcp")` calls with your own API.
