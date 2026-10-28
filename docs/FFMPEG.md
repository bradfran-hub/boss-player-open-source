# FFmpeg source and rebuild guide

## Historical FFmpeg dependency subset

Extract `boss-ffmpeg-upstream-and-patches-v4.tar.gz` and enter `FFmpeg-dependency`.

This dependency subset retains complete FFmpeg n8.0.1 source at revision `894da5ca7d742e4429ffb2af534fcda0103ef593`, selected FFmpeg patches, an attachment-limit header, configure options, recorded configurations and an FFmpeg-only build recipe. The upstream archive includes its licences. A new subset manifest describes the selected inputs; it does not impersonate the complete historical kit's manifest.

Requirements: a Mac, Python 3, Xcode command-line tools and make. Select an installed Xcode using `DEVELOPER_DIR` or `xcode-select` before building.

Verify the source manifest:

```sh
python3 Scripts/build.py --verify-only
```

Build a library variant in a fresh, recipient-selected directory:

```sh
python3 Scripts/build.py --build-root /tmp/boss-recipient-build --variant macos-arm64 --jobs 2
```

Run `python3 Scripts/build.py --help` for iOS, tvOS, simulator and Catalyst recipe routes. These names describe recipe routes, not acceptance evidence for all platforms. The original configure and patch information is inside the archive.

The recipe builds FFmpeg libraries only. It does not build the BOSS SDK or relink/reinstall Odyssey. Those final-application distribution materials remain a separate requirement.

## Later source snapshot

`boss-ffmpeg-current-source-20261028.tar.gz` supplies the later expanded FFmpeg source tree used for the Catalyst native media build and the mobile Matroska audio patch. It does not include the full BOSS SDK or proprietary application. The additional-materials archive includes retained caption adaptations and separate FFmpeg-related native source files.

## Current snapshot rebuild recipe

Download `boss-ffmpeg-current-rebuild-recipe-20261028.zip` and `boss-ffmpeg-current-source-20261028.tar.gz` from the [versioned source release](https://github.com/bradfran-hub/boss-player-open-source/releases/tag/sources-2026-10-28). Verify both against [SHA256SUMS](../SHA256SUMS), then extract the recipe ZIP and follow its README.

Requirements: macOS, Python 3, Xcode with the target platform SDK, and make. Select Xcode using `DEVELOPER_DIR` or `xcode-select`. The recipe runs offline and refuses to overwrite an existing build directory. Use a new build directory without spaces; an Xcode installation path containing spaces is supported.

Verify the current source archive without compiling:

```sh
python3 rebuild.py --source-archive /path/to/boss-ffmpeg-current-source-20261028.tar.gz --configure-options configure-options.json --variant ios-arm64 --build-root /tmp/boss-ffmpeg-check --verify-only
```

Build a library variant:

```sh
python3 rebuild.py --source-archive /path/to/boss-ffmpeg-current-source-20261028.tar.gz --configure-options configure-options.json --variant ios-arm64 --build-root /tmp/boss-ffmpeg-ios --jobs 2
```

The variants are `ios-arm64`, `tvos-arm64`, `maccatalyst-arm64` and `maccatalyst-x86_64`; use a separate new build directory for each. Each produces `libavformat.a`, `libavcodec.a`, `libavutil.a`, `libswresample.a` and `libswscale.a` under `install/lib`, plus commands, logs and a build receipt.

Local builds succeeded for all four routes using Apple clang 21 and Xcode 27.0 SDKs. The recipe ZIP includes sanitized per-route output hashes and licence-configuration evidence. Verification checks the source archive hash, complete file membership and all 9,917 recorded source files. The recipe's own GPL-3.0-or-later licence does not change FFmpeg's applicable file licences.

These are dependency-only build results. They do not prove byte identity with shipping libraries, complete source correspondence for every retained mobile native object, or a recipient's ability to relink, install and use Odyssey. Final-binary correspondence and application relink/replacement delivery remain open. No tested playback implementation was replaced by this publication.

FFmpeg's upstream software licence has no mandatory purchase fee. Distribution obligations still apply. Primary guidance: https://ffmpeg.org/legal.html
