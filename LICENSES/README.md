# Licence scope and notices

The upstream source archives preserve copyright notices and licence texts. Read the notices in each source file and dependency; this directory is a convenience, not a replacement for those notices.

| Component | Terms retained in this publication |
| --- | --- |
| FFmpeg n8.0.1/BOSS native build | LGPL-2.1-or-later configuration in the retained BOSS source kit; GPL and nonfree are disabled in that kit. Upstream optional code retains its own terms. |
| VLC/libVLC | See `VLC-COPYING.LIB.txt`, `VLC-COPYING.txt` and individual source/module notices. Do not infer the entire linked dependency graph from the core library's licence. |
| VLCKit | `VLCKit-COPYING.txt` and source headers retain LGPL-2.1-or-later terms. |
| FFmpeg-only build script | The extracted recipe carries GPL-3.0-or-later. This script's licence does not license the whole BOSS SDK. |
| BOSS caption adaptations | Preserve the applicable LGPL/third-party notices; BOSS's commercial offer does not override these notices. |
| VLC contrib packages | Each original source archive contains its own applicable notices; the contrib rules include patches and build recipes. Source-cache presence is not a statement that every package is linked. |

FFmpeg copyright and credits are preserved in its source, including `COPYING.*`, `LICENSE.md` and file headers. VLC authors, VideoLAN, VideoLabs and VLCKit contributors retain the copyrights identified by their sources. No Dolby certification, patent licence or Apple-platform permission is granted by publishing this repository.

This repository contains no paid KSPlayer or private FFmpegKit edition and does not grant rights to those packages.

Additional speech, translation, network, disc and Rust dependency notices are in the additional-materials archive. See `docs/DEPENDENCIES.md` for version evidence and unresolved items. A BOSS payment never replaces a dependency's required source, notices or recipient rights.

## Offline notice collection

The versioned source release also contains `boss-dependency-notices-20261028.zip`: seven readable documents assembled from 194 retained source records. It includes separate disclosures for BOSS FFmpeg and the KSPlayer/FFmpegKit stack, VLC/contrib, translation, Rust/Dolby dependencies and Google Cast. This collection is a source superset; it is not proof that every listed dependency is linked into every platform.

SwiftDraw 0.29.0's [original zlib notice](SwiftDraw-zlib.txt) is retained from revision `82699f4bdf2f075793cfa0d392eb27c59b41a3fe`. [Upstream original](https://github.com/swhitty/SwiftDraw/blob/82699f4bdf2f075793cfa0d392eb27c59b41a3fe/LICENSE.txt).

The current FFmpeg rebuild ZIP retains a separate full build-script licence and verification receipts. Required final app-bundle delivery, complete linked-membership review and unresolved rights remain separate work. These materials do not grant a proprietary exception to third-party GPL/LGPL code.

The newer `boss-third-party-notices-current-20261028-r3.zip` retains eight current notice resources and their platform scopes, plus original nlohmann/json contributor, fmt, network/RPC and RSA-MD4 notice supplements. It does not replace the earlier archived notice snapshot or establish that a newly distributed app includes these updates.
