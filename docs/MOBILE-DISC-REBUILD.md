# libbluray / libudfread iOS and tvOS dependency rebuild

Dependency-only material prepared on 28 October 2026. Download
`boss-disc-mobile-rebuild-recipe-20261028.zip` from the
[versioned dependency release](https://github.com/bradfran-hub/boss-player-open-source/releases/tag/sources-2026-10-28).
It contains the original libbluray 1.4.1 archive (including
libudfread), the existing dependency source patch, retained generated headers,
compiler plans and an offline build recipe. It contains no private BOSS wrapper,
Odyssey implementation, proprietary compiled objects, signing data or keys.

## Build

Use macOS, Python 3 and Apple's Xcode tools with the iOS/tvOS device SDKs. The
recipe does not download anything or require Meson, Ninja or Python packages.
Verify SHA256SUMS first, then run:

```sh
python3 rebuild.py --output /absolute/path/to/new-mobile-disc-build --platform both --jobs 3
```

The output must be a new directory, separate from this package. Select `ios` or
`tvos` to build a single platform. The retained targets are arm64 iOS 16.0 and
arm64 tvOS 16.0. Simulator and Catalyst architectures are outside this package.

The script verifies input hashes, unpacks the source archive, applies the
existing patch, restores seven generated configuration/public headers and
compiles 59 dependency objects per target. Outputs are:

- `install/ios-arm64/lib/libbluray.a` and `libudfread.a`
- `install/tvos-arm64/lib/libbluray.a` and `libudfread.a`
- `receipt.json`, recording compiler, SDK and input/output hashes

The libbluray archive includes its four libudfread objects. A separate
libudfread archive is supplied for matching client link recipes. This package
does not change Odyssey's retained archive composition or final app linkage.

The existing adaptation patch has a historical Catalyst name. Its disabled
mount discovery and BD-J implementations match the retained mobile adaptation
files. The recipe copies those exact patched files into the expected mobile
build layout; it does not introduce a new implementation or disc-menu feature.

## Reproducibility

Compiler `__FILE__` strings can include an absolute source directory. The
default recipe replaces that directory with `/dependency-source` so it does not
expose a developer's private filesystem path. `--compiled-source-prefix` can
select a different string prefix; it never changes where source files are read.

Both targets were built with Apple clang 21.0.0 (clang-2100.3.34.2) and the
selected Xcode device SDKs. With the original recorded source-string prefix,
all 59 iOS and all 59 tvOS dependency objects were byte-for-byte identical to
the retained build inputs. The portable default prefix changes source-path
strings; those outputs must not be described as wholly byte-identical. See
VERIFICATION.json for the verified comparison scope and results.

## Limits and licences

This package rebuilds these dependency archives. It does not rebuild the
private BOSSDisc wrapper or final application, sign/install an app, establish
playback acceptance, or settle remaining distribution-rights questions.

Preserve the dependency notices, original source modifications and applicable
licences, including `COPYING` and `contrib/libudfread/COPYING` in the source
archive. Other source-file notices remain intact. The build recipe itself is
GPL-3.0-or-later; its full licence is in LICENSE-BUILD-RECIPE.txt. This does not
relicense the dependencies or BOSS/Odyssey.

The ZIP preserves its preparation-time README and verification records. Publication status is recorded by this repository and release. No installed app is updated by this package.
