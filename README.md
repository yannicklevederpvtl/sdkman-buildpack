# sdkman-buildpack

Cloud Foundry supply buildpack: installs [SDKMAN](https://sdkman.io/) and requested SDKs (Java, Kotlin) at build time.

- **Detect:** when app has `sdkman.yml`.
- **Supply:** installs SDKMAN and runs `sdk install` for entries in `sdkman.yml`; writes `sdkman-env.sh`.
- **Runtime:** app sources `$HOME/deps/0/sdkman/sdkman-env.sh` (index 0 when this buildpack is first).

**Minimal usage:** Add `sdkman.yml` in app root (see `sdkman.yml.example`), list this buildpack first in manifest, then source the env script in your start command.
