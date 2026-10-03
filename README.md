# cargo-reusable
The reusable rust:host and cargo:host (cargo-reusable package) repository used by LibreELEC.

Each release is tagged `<OS_VERSION>-<rust version>` and holds one archive per
build host and target:

    cargo-reusable-<OS_VERSION>-<rust>-<host>-<TARGET_NAME>-<hash>.tar.xz

`<hash>` is taken from the rust and cargo `package.mk`, so a recipe change in
LibreELEC.tv names a different archive and an old one is never used. A
`MANIFEST` in each archive records the llvm, gcc, glibc and openssl versions it
was built with.

LibreELEC.tv uses it with `USE_REUSABLE="preferred"` (or `"yes"`), and builds
it with `BUILD_REUSABLE="cargo:host"`.
