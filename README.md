# Etherpad LazyCat community package

Upstream: https://github.com/ether/etherpad (formerly ether/etherpad-lite). Official candidate cloud.lazycat.app.etherpad1. Package community.lazycat.app.etherpad,3.3.12, minOS1.6.0 for run_as UID mapping; linux/amd64 mirror delivery, community store only. Intended classification Office / Docs95.

Two upstream containers: Etherpad HTTP9001 and internal PostgreSQL15-alpine. Persistent database, plugin directory and application var directory. run_as5001:0 matches upstream user, only on Etherpad; database keeps its upstream entrypoint. No added healthcheck/smoke startup gate.

LazyCat authentication remains mandatory; editing has no separate user isolation. Only grant app access to trusted collaborators: /admin uses shared admin credentials from deployment parameters and automatic fill (not submit). Plugins execute code and need review. settings.json edits through admin are not separately bind-mounted and may reset when containers are replaced; use deployment parameters for passwords. No LibreOffice converter.

No file interception. No real-device startup, database initialization, admin fill, multi-user editing, plugins, backup or persistence testing.

Initial full dedup7pages624unique apps, no name/alias/package/source matches. Refresh before publication and independently verify category95.
