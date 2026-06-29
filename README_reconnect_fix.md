# RoRBot reconnect fix

Changes included:

- Resets the reconnect attempt counter after every successful RoR server connection.
- Stops temporary reconnect failures from posting `Couldn't connect to server (#ERROR_CON001/#ERROR_CON002)` into Discord.
- Stops `Lost connection to server (#ERROR_CON003)` from posting into Discord during normal restart/reconnect cycles.
- Keeps the final Discord error only if all reconnect attempts are exhausted.
- Suppresses server MOTD lines from Discord when the bot reconnects, preventing restart spam like `unknown(-1): MOTD: ...`.
- Increases default reconnect behavior from 3 tries every 5 seconds to 30 tries every 10 seconds.
- Adds optional XML support:

```xml
<reconnect interval="10" tries="30" />
```

This tag can be placed inside an individual `<RoRclient>` entry or the `default/template` entry.
