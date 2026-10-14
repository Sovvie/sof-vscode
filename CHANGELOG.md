# Changelog

## 0.1.2

- **New default registry.** The sof registry moved to https://sof.sov.gg, so that is where the extension looks when `sof.registryUrl` and `SOF_REGISTRY_URL` are both empty. A setting or environment variable that still names the old address keeps pointing there and should be changed.

## 0.1.1

- **Hover card tidied.** One card, not two when hovering where the tag sits; each fact is stated once; the verdict is coloured with the same theme colours as the tags (so `workbench.colorCustomizations` for `sof.tag.*` applies to both).
- **Install check.** New violet tags, `⟳ installed 1.0.0` and `⟳ not installed`, show when `sof.lock` has not caught up with `sof.toml` (a bumped range, or a dependency added since the last install). The hover explains it and links to the install, the status bar says `⟳ N to install`, and `sof.diagnostics.outdated` can report it as a diagnostic.
- **sof: Run Install** command: opens a terminal in the file's folder and runs `sof run package install`.
- Fixed: a malformed specifier no longer leaves the status bar spinning.

## 0.1.0

First version.

- Inline tags after each dependency in `sof.toml`, `.sof.toml` and `*.sof.toml`: `✓ latest`, `↑ 2.0.0`, `✗ no match`, `✗ yanked`, `not in index`.
- Lockfile-aware: a dependency is "on" the version `sof.lock` pins, like `sof run package outdated`.
- Hover cards with the range, what it resolves to, versions, license, authors and dependencies.
- Completion for package names, versions after `@`, and whole `Alias = "scope/name@^x.y.z"` lines.
- Diagnostics for invalid specifiers, unknown packages, ranges nothing satisfies, and yanked versions.
- Quick fixes to update one dependency or all of them; `sof: Update Dependencies...`.
- Status bar summary of the active file.
- **Output > sof** channel: one line per analysed file, and registry errors.
- Wally fallback for packages the sof index does not hold, as the CLI does.
