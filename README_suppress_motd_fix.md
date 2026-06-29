# RoRBot reconnect / unknown(-1) / MOTD suppression fix

This build includes the previous reconnect stability fixes, source `-1` normalization, and suppresses RoR `MOTD:` chat lines from Discord on connect/reconnect.

Expected Discord behavior after connect/reconnect:
- `[info] Connected to server <name>` still posts.
- MOTD lines are not reposted.
- Normal player chat and game join/leave events still post.
