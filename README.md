# BOSS Player open-source materials

FFmpeg, VLC/libVLC and VLCKit source materials used in the development of BOSS Player for Odyssey on Apple TV, iPhone/iPad and Mac.

## Downloads

Download the source archives from [Sources — 28 October 2026](https://github.com/bradfran-hub/boss-player-open-source/releases/tag/sources-2026-10-28). No payment or private repository access is required for these published materials.

| Download | Contents |
| --- | --- |
| `boss-ffmpeg-upstream-and-patches-v4.tar.gz` | Complete pinned FFmpeg n8.0.1 upstream source, historical FFmpeg changes, recorded configurations and an FFmpeg-only build recipe. This is a dependency subset, not the full historical BOSS relink kit. |
| `boss-ffmpeg-current-source-20261028.tar.gz` | Later expanded FFmpeg source used for Mac Catalyst and the retained mobile Matroska audio patch. |
| `boss-mobile-vlc-source-20261028.tar.gz` | Retained VLC source snapshot for the mobile build route. |
| `boss-mobile-wrapper-source-20261028.tar.gz` | Retained VLCKit wrapper source snapshot for the mobile build route. |
| `boss-catalyst-vlc-source-20261028.tar.gz` | Mac Catalyst VLC source snapshot, including the applied source changes. |
| `boss-catalyst-wrapper-source-20261028.tar.gz` | Mac Catalyst VLCKit wrapper snapshot, including the applied source changes. |
| `boss-vlc-contrib-source-cache-20261028.tar` | Upstream source archives retained by the VLC dependency build. A cached package is not necessarily linked into every app. |
| `boss-additional-dependency-materials-20261028.tar.gz` | Available network-library source/build materials, caption adaptations, Dolby parser dependency sources, disc-reader source and speech/translation copyright and licence notices. See the dependency inventory for coverage limits. |

Check downloads with [SHA256SUMS](SHA256SUMS). Each archive also includes `SOURCE-FILES.json`, listing its source files and hashes. [Source asset metadata](manifests/source-assets.json) records archive sizes and hashes.

## Build and licence information

- [FFmpeg source and rebuild guide](docs/FFMPEG.md)
- [VLC and VLCKit source and rebuild guide](docs/VLC.md)
- [Licences and copyright notices](LICENSES/README.md)
- [Recorded build coverage](manifests/build-coverage.json)
- [Remaining distribution work](docs/DISTRIBUTION-STATUS.md)
- [All-dependency inventory and both-edition requirements](docs/DEPENDENCIES.md)
- [BOSS edition licensing policy and limits](docs/EDITION-LICENSING.md)

Upstream licences and individual file notices remain in force. FFmpeg, VLC and their dependencies are not relicensed under a blanket BOSS licence. GPL text is retained where supplied by upstream; its presence in a source archive does not mean all GPL modules are linked into an app. This dependency repository does not grant a new licence to the complete BOSS SDK. Existing GPL/LGPL grants are not withdrawn or restricted by it.

## Scope of this publication

This repository provides dependency source materials, patches and build information. It does not contain Odyssey account data, media credentials, licensed films, Apple signing keys, private KSPlayer code or the Odyssey application's private source.

The final app's required relinking/replacement materials, installation instructions, final-binary correspondence checks and distribution review are still pending as recorded in the coverage manifest. This publication does not claim that those remaining tasks have been completed. No complete BOSS SDK or Odyssey application source release is made here.

In-app attributions and this source publication serve different purposes. Existing Odyssey attributions should link to this repository and identify the version of the relevant source materials.
