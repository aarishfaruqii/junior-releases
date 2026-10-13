# Junior

A free, local-first macOS notch utility: a notch panel (left, right or top)
with a Now page (player, network and data usage, screen time, calendar,
tasks, weather), a toolkit, a shelf with clipboard history, fixes, and a
volume / brightness HUD that can replace the system one.

- `PRD.md`: the product. `FEATURES.md`: every feature, how it works, and
  its confidence (including what was added in October 2026).
- `HANDOFF.md`: current status. `AUDIT-FINAL.md`: the latest audit
  (pass / fail / not tested, findings and fixes). `DECISIONS.md`: every
  decision and measurement, newest last.

```
make dev    # build and launch build/Junior.app (debug)
make test   # run the Swift Testing suite, then JuniorProbe verify
```

Debug builds include `Scripts/junior-debug.swift` (open tabs, fake player
tracks, HUD levels, glass scrim, screen-change handler… for screenshots and
tests without real input).

## Privacy

Everything stays on the Mac. The only network calls are Open-Meteo (weather
and city lookup). Clipboard history is encrypted at rest with a key in
Keychain. Screen time records app names only, never window titles.

## Acknowledgements

- **[mediaremote-adapter](https://github.com/ungive/mediaremote-adapter)** by
  Jonas van den Berg and contributors (BSD 3-Clause) — lets Junior read and
  control the system Now Playing (any app, including browsers) on macOS 15.4+.
  Vendored unmodified in `ThirdParty/mediaremote-adapter/`, licence included.
