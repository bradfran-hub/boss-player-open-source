# VLC, libVLC and VLCKit source materials

## Revisions and patches

The retained source roots use:

- VLC: `a0c13fc0c1557eea850d9bcac3b07798a38454b0`
- VLCKit wrapper: `4597608200216a4393fb1b5d2e7eaade0b774187`

The mobile and Catalyst snapshots are separate because Catalyst has additional applied source changes. [The snapshot manifest](../manifests/vlc-source-snapshots.json) records each base commit, patch and file count. The source archives already include the recorded working-tree changes; do not apply the patch again to an extracted snapshot. The patches are useful when comparing against an independently obtained clean upstream revision.

Each source snapshot contains the tracked source at the recorded revision plus tracked modifications, with original copyright and licence notices. Build products and Git credentials/history are excluded.

## Source layout and build routes

Extract a matching VLC and wrapper snapshot into a recipient-controlled directory. Provide the VLC tree as `Wrapper/libvlc/vlc`, as expected by VLCKit's build script. Extract the contrib source-cache archive so its contents are at `VLC/contrib/tarballs`.

The wrapper's `compileAndBuildVLCKit.sh`, VLC's `extras/package/apple/build.sh`, their source documentation and the contrib `rules.mak`/patch files contain the upstream build routes. Inspect the scripts' help before selecting the SDK and architecture. A compatible Xcode, compiler, autotools, make, Python and the source-specified auxiliary tools are required; some contrib recipes also require Rust or an assembler.

[Recorded configure commands and generated configuration headers](../configurations/) are provided for the retained mobile and Catalyst build directories. `${...}` in those records denotes a recipient-selected local directory. Recorded commands are configuration evidence, not drop-in commands containing the original developer's machine paths.

The contrib source cache retains original dependency source archives, including FFmpeg used inside VLC. The standalone BOSS FFmpeg source kit and VLC's own FFmpeg dependency are different builds and must not be treated as interchangeable. A source archive cached for a recipe is not evidence that its package was linked into every application.

## Verification still required

Publishing the retained source does not establish that each final app's embedded VLC library was rebuilt from this precise snapshot. The final platform-specific mapping, complete VLC/contrib module licence audit, portable clean rebuild and complete application replacement/relink route are tracked in [distribution status](DISTRIBUTION-STATUS.md).

libVLC/VLCKit source includes LGPL terms, while other VLC modules and contrib dependencies retain their own terms. Preserve per-file notices and check the modules actually linked instead of applying a blanket LGPL label to the full archive.
