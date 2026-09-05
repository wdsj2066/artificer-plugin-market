# Artificer Plugin Market

Static plugin registry for [Artificer](https://github.com/wdsj2066/Artificer).

This repository intentionally has no backend. The client reads `registry.json`, and each plugin package is distributed through a GitHub Release or another HTTPS URL.

## Repository layout

- `registry.json`: client-facing plugin index
- `schema/registry.schema.json`: registry validation schema
- `CONTRIBUTING.md`: plugin submission requirements

Each registry entry describes one released plugin package. `downloadUrl` points to a versioned archive, and `sha256` is the SHA-256 digest of that exact file.

Backend plugins must declare `hasBackend: true` and list every requested permission. They execute with host process privileges and require review before listing.

## Client endpoint

```text
https://raw.githubusercontent.com/wdsj2066/artificer-plugin-market/main/registry.json
```

The client should treat the registry as untrusted input: validate the manifest, verify the archive digest, extract into a temporary directory, and only then install and build the plugin.