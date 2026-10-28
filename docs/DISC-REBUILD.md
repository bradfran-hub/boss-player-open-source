# libbluray / libudfread dependency rebuild

Dependency-only recipient material, prepared 28 October 2026. Download
`boss-disc-catalyst-rebuild-recipe-20261028.zip` from the
[versioned dependency release](https://github.com/bradfran-hub/boss-player-open-source/releases/tag/sources-2026-10-28).

This package contains the retained libbluray 1.4.1 source archive (including
libudfread), the supplied Catalyst source patch, architecture-specific generated
configuration/public headers, and an offline compiler recipe. It contains no
BOSSDisc wrapper, Odyssey/BOSS application source, proprietary objects,
credentials or signing profiles.

## Rebuild

Use macOS with Apple's Xcode command-line tools and Python 3. No Meson, Ninja,
network download or additional Python package is required by this replay recipe.
Check the package's SHA256SUMS before running it. Keep the selected Xcode and
SDK version in the resulting receipt.

```sh
python3 rebuild.py --output /absolute/path/to/new-disc-rebuild --arch both --jobs 3
```

The output directory must not exist and must be separate from this package.
`--arch arm64` and `--arch x86_64` select one Catalyst architecture. This recipe
does not make iOS-device, tvOS-device or AppKit slices.

The script checks all recorded source-input hashes, safely unpacks regular
source files, applies the dependency patch, restores the retained generated
configuration, compiles 59 dependency objects per architecture, and produces:

- `install/arm64/lib/libbluray.a` and `libudfread.a`
- `install/x86_64/lib/libbluray.a` and `libudfread.a`
- `receipt.json` with compiler, SDK, input and output hashes

The retained Meson libbluray target includes its libudfread objects. The separate
libudfread archive is also supplied for clients that require it. A client should
follow its matching link recipe when choosing the archives; this package does
not change Odyssey's existing link composition.

## Verified result and limits

With Apple clang version 21.0.0 (clang-2100.3.34.2) and the retained MacOSX 27.0 SDK, the fresh outputs were
compared individually with all retained dependency objects from the Mac build:
59/59 arm64 and 59/59 x86_64 were byte-for-byte identical. See VERIFICATION.json.
The source graph check covered 138 distinct dependency source/header files.
The original source archive plus supplied patch matched those files, and both
root licence texts are present in Odyssey's current staged app notice resource.

That evidence covers these dependencies and the retained Mac build inputs. It
does not establish the whole final application's source correspondence, a
mobile rebuild, playback acceptance, any new distribution right, or complete
compliance for Odyssey or either BOSS edition. It does not bypass application
purchase, platform signing or protected-storage requirements.

## Licences

The dependencies retain the original applicable terms in the source archive,
including `COPYING` and `contrib/libudfread/COPYING`. Preserve the original
notices and the supplied source modifications when redistributing them. The
build recipe is GPL-3.0-or-later; its full licence is included as
LICENSE-BUILD-RECIPE.txt. That recipe licence does not relicense the dependencies
or the separately distributed BOSS/Odyssey implementation.

The supplied patch records the retained adaptations: external runtime library
loading and macOS physical-device discovery are disabled, with the retained
BD-J-disabled configuration. These are the existing dependency settings. This
rebuild does not introduce new playback behaviour.
