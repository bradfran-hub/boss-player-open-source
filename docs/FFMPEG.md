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

The current snapshot is source material. Its complete portable rebuild recipe, source-to-final-binary verification and application relink delivery remain pending. Do not represent a historical kit build as a byte-for-byte reproduction of a later Odyssey binary.

FFmpeg's upstream software licence has no mandatory purchase fee. Distribution obligations still apply. Primary guidance: https://ffmpeg.org/legal.html
