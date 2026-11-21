# Snell v6 support

This fork tracks [chen08209/FlClash](https://github.com/chen08209/FlClash) `main`.
Snell v6 now ships in the upstream core (mihomo #3410), so `core/Clash.Meta` is the upstream submodule, unchanged.

The fork adds only:

- In-app updates from this repository's releases, with automatic download and install on exit or when idle (Windows).
- `.github/workflows/release.yaml`, which builds and publishes the Windows installers on a `v*` tag.

```yaml
proxies:
  - {name: snell-v6-a, type: snell, server: a.example.com, port: 7177, psk: your-psk, version: 6, mode: default, udp: true}
  - {name: snell-v6-b, type: snell, server: b.example.com, port: 7177, psk: your-psk, version: 6, mode: default, udp: true}
  - {name: snell-v6-c, type: snell, server: c.example.com, port: 7177, psk: your-psk, version: 6, mode: default, udp: true}

proxy-groups:
  - {name: PROXY, type: select, proxies: [snell-v6-a, snell-v6-b, snell-v6-c]}

rules:
  - MATCH,PROXY
```

`mode` is one of `default`, `unshaped`, `unsafe-raw` and must match the server. v6 does not support the `http` and `tls` obfs modes.

Licensed under GPL-3.0, same as upstream.
