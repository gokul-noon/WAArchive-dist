# WAArchive-dist

Public signed releases and Sparkle update feed for WA Archive.

Apple Silicon, macOS 14 or later.

## Install

1. Download `WAArchive.dmg` and `WAArchive.dmg.sha256` from the
   [latest release](../../releases/latest).
2. Verify the download:

   ```sh
   shasum -a 256 -c WAArchive.dmg.sha256
   ```

3. Open the DMG and drag WA Archive into Applications.

The app updates itself afterwards through Sparkle, fed by
[`appcast.xml`](appcast.xml) in this repository. Every update is signed with
the project's Ed25519 update key and verified on the machine before install.

Each release also carries `WAArchive.provenance.json`, recording the source
commit, build number, and artifact digest the release was built from.

## Source

WA Archive's source lives in a private repository; this repository holds only
signed artifacts and the update feed. Release tags follow
`v<marketing>-<build>`. The corresponding-source terms for the GPL components
ship with the first published release, on counsel's recorded terms.
