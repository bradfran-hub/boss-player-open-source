# Distribution status — 28 October 2026

This is a source-material publication, not a legal-compliance certification. The current FFmpeg recipe demonstrates library rebuilds, not final app correspondence or recipient installation. Existing tested playback code has not been replaced by this licensing publication.

## Supplied here

- Complete historical FFmpeg upstream source, selected patches and FFmpeg-only build recipe with a dependency-subset manifest.
- Later FFmpeg source snapshot and mobile audio patch, plus an offline rebuild recipe with successful iOS arm64, tvOS arm64 and Catalyst arm64/x86_64 library builds.
- Retained mobile and Catalyst VLC/VLCKit source snapshots and source changes.
- Original VLC contrib dependency source-cache archives.
- Licence texts, recorded configure commands, source-file hashes and asset checksums.
- A build coverage manifest that keeps unverified items explicit.
- Additional available dependency sources/notices and a both-edition dependency checklist.
- Seven offline notice documents from 194 retained source records, with document hashes and provenance; the original SwiftDraw zlib notice is also retained in the repository.

## Remaining work before declaring the complete shipped app covered

1. Match every FFmpeg, BOSSRemux, BOSSFELDecode and VLC/VLCKit binary in each distributed build to the exact source snapshot, changes, configuration and build tools. Reconcile the later mobile/FEL/Dolby patches with the historical source kit.
2. Complete the licence audit of the VLC modules and contrib packages actually linked into each app, including VLC's own FFmpeg build. Resolve any GPL/nonfree components or uncertain provenance before calling the complete binary LGPL-only.
3. Publish the final corresponding library sources, build scripts, changes and required objects/materials for the real Odyssey application. An FFmpeg-only build is not an application relink package.
4. Verify a recipient can modify the relevant library, rebuild/relink the actual application and use the resulting app through the applicable Apple-platform installation/signing process. No developer private signing key is published.
5. Confirm the applicable LGPL versions, app terms and App Store distribution mechanism preserve recipient rights. Review installation information where required. Get qualified advice for unresolved distribution/licensing questions.
6. Link the existing in-app attributions to the versioned source downloads and ensure the actual app bundles include the required licence texts. Review the other bundled libraries separately; this repository's FFmpeg/VLC focus does not close every dependency's obligations.
7. Review KSPlayer/FFmpegKit separately under the author's applicable grant. No payment or private LGPL grant is established by this repository, and no private paid code is included here.
8. Close every additional dependency item in `DEPENDENCIES.md` for the exact Free and paid artefacts, including models, Rust crates, speech, network/disc libraries and adapted source. Resolve ownership and historical grants before offering a new commercial BOSS licence. A paid edition and a free edition each need their own final dependency manifest and distribution evidence.

The local archives inventoried were Odyssey 2.101 builds 1294 (tvOS), 1301 (iOS/iPadOS) and 1302 (Mac Catalyst). These labels do not identify the currently approved or publicly available App Store build. No app submission, installation, device playback or app binary is changed by this source publication.
