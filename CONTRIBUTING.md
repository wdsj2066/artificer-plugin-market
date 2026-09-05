# Contributing a Plugin

1. Publish the plugin source in a public GitHub repository.
2. Publish a versioned `.zip` package in a GitHub Release.
3. Ensure the archive contains one top-level plugin directory with `plugin.json`.
4. Confirm the manifest `id` matches the directory name and the registry entry.
5. Declare `engines.artificer`, `hasBackend`, and all required permissions.
6. Calculate SHA-256 for the exact release asset and add it to `registry.json`.
7. Open a pull request with installation and security notes.

Plugins with `server.js`, routes, hooks, channels, subprocess access, or filesystem access require manual review. Do not include secrets, `node_modules`, or package managers in plugin archives.