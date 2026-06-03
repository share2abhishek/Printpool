# Releasing Radixile PrintPool

How to cut a new version and publish it to **Bitbucket Downloads**.

## Versioning

We use [Semantic Versioning](https://semver.org/): `MAJOR.MINOR.PATCH`.
- **PATCH** — bug fixes only (1.0.0 → 1.0.1)
- **MINOR** — new features, backward compatible (1.0.1 → 1.1.0)
- **MAJOR** — breaking changes (1.x → 2.0.0)

The single source of truth is the `version` field in `package.json`. It drives:
- the installer file name (`printpool-<version>-setup.exe`),
- the executable's version resource (shown in file Properties),
- the auto-update feed (if/when enabled).

## Release steps

1. **Update the changelog.** Add a new section at the top of `CHANGELOG.md` describing
   what changed (Added / Changed / Fixed / Removed).

2. **Bump the version.** This updates `package.json` and creates a git commit + tag:
   ```bash
   npm version patch     # or: minor | major
   ```
   (Use `npm version patch -m "release: %s"` to customise the commit message.)

3. **Build the installer.**
   ```bash
   npm run build:win:bundle      # Windows, self-contained → dist/
   # On a Mac, additionally: npm run build:mac:bundle
   ```

4. **Publish to GitHub Releases (public download — recommended).**
   Create a GitHub **Personal Access Token** (classic: `repo` scope, or fine-grained with
   **Contents: Read and write**), then:
   ```bash
   set GH_TOKEN=<token>
   npm run publish:github
   ```
   This creates the public repo **share2abhishek/printpool** (if missing), makes a release
   `v<version>`, and uploads the installer. **Anyone can download it without a login:**
   `https://github.com/share2abhishek/printpool/releases/download/v<version>/printpool-<version>-setup.exe`
   (Override the target with `GH_OWNER` / `GH_REPO`.)

   *Alternative — Bitbucket Downloads* (private; only repo collaborators can download):
   create a Bitbucket **App password** (Repositories: Write), then
   `set BITBUCKET_USER=… & set BITBUCKET_APP_PASSWORD=… & npm run publish:bitbucket`.

5. **Push code + tags** (so the tag and changelog are on the remote):
   ```bash
   git push && git push --tags
   ```

## Notes

- The Windows build is currently **unsigned** → first-run SmartScreen warning. A
  code-signing certificate removes it; see the distribution options in the project notes.
- macOS `.dmg` must be built on a Mac (electron-builder can't cross-compile/sign it from
  Windows). `build/entitlements.mac.plist` is included for the hardened runtime.
- Bitbucket Downloads keeps every uploaded file; re-uploading the same filename overwrites it.
