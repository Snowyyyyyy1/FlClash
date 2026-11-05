# Snell v6 support

This is [chen08209/FlClash](https://github.com/chen08209/FlClash) v0.9.2 with Snell v6 added to the core.
The only functional change is the `core/Clash.Meta` submodule, which points to the
[`snell-v6` branch](https://github.com/Snowyyyyyy1/Clash.Meta/tree/snell-v6) of a Clash.Meta fork.
See `core/Clash.Meta/SNELL_V6.md` for the config syntax:

```yaml
proxies:
  - {name: snell-v6, type: snell, server: example.com, port: 443, psk: your-psk, version: 6, mode: default, udp: true}
```

`mode` is one of `default`, `unshaped`, `unsafe-raw`. QUIC works as UDP traffic over the v6 relay.

Licensed under GPL-3.0, same as upstream.
