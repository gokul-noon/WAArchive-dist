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

3. Open the DMG and drag WA Archive into Applications. Run it from there, not
   from the disk image. macOS keeps a downloaded app read-only until you move
   it, and an update cannot install over a read-only copy.
4. macOS asks you to confirm the first time you open it. Click Open. It says
   Apple checked the app and found no malicious software, and you see that
   once.

The app updates itself afterwards through Sparkle, fed by
[`appcast.xml`](appcast.xml) in this repository. Every update is signed with
the project's Ed25519 update key and verified on the machine before install.

Each release also carries `WAArchive.provenance.json`, recording the source
commit, build number, and artifact digest the release was built from.

## Source

Every release carries `WAArchive-source.tar.gz`, the corresponding source for
the GPL-licensed device transport: the Python acquisition helper, the pinned
source distribution of every package it depends on, and the scripts that build
and install that runtime. `NOTICE-device-transport.md` inside the app names
that archive by release tag and SHA-256, so you can check that the source
beside a download is the source that built it.

WA Archive's own source lives in a private repository. This repository holds
the update feed and the signed release assets, nothing else. Release tags
follow `v<marketing>-<build>`.
