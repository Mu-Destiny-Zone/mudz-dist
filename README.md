# mudz-dist

Published output for the Mu Destiny Zone client pipeline, served by GitHub Pages.

```
update-test/    test channel  -- update.json + the manifested files
update/         prod channel
launcher/       the news page rendered in the launcher's webview
.nojekyll       required: Jekyll silently drops underscore-prefixed paths, and the
                client ships Scripts/_fullscreen_mode.reg and _window_mode.reg
```

Everything here is written by `mudz-build publish`. Do not edit by hand — the launcher
validates every file against `update.json`, so a hand edit shows up as a checksum
failure on a player's machine.

Only files listed in `update.json` are published. Anything else in the payload matches
the baseline by definition and already lives in the client zip, so publishing it would
grow this repo for no benefit.

**This is separate from production.** The live client is served from
`Mu-Destiny-Zone-Easy` via `update.mudestinyzone.com`; nothing here affects it until a
launcher build pointed at these URLs actually ships.
