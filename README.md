# c2pac-binaries

Prebuilt `C2PAC.xcframework` static libraries: the C API of
[contentauth/c2pa-rs](https://github.com/contentauth/c2pa-rs), with one small patch,
packaged for Swift Package Manager `binaryTarget`s.

Each release carries one `C2PAC.xcframework.zip` with its SwiftPM checksum in the release
notes.

## c2pac-v0.90.0-routing.1
- Source: c2pa-rs tag `c2pa-v0.90.0` (`a93bb4357d4a3a24e6f70186b184be47d928db9a`).
- Patch: [`patches/c2pa-v0.90.0-context-timestamp.patch`](patches/c2pa-v0.90.0-context-timestamp.patch).
  RFC 3161 timestamp requests go through the builder's operation context and a
  header-aware resolver.
- Build: Rust 1.99.0, release profile, LTO off, features
  `rust_native_crypto,add_thumbnails,http,file_io`; iOS / Mac Catalyst 17.0, macOS 14.0.
  Build-host paths are remapped out of the binary.
- Slices: iOS arm64; iOS Simulator arm64 + x86_64; Mac Catalyst arm64 + x86_64;
  macOS arm64 + x86_64.

## License
c2pa-rs is dual-licensed under [MIT](LICENSE-MIT) or [Apache-2.0](LICENSE-APACHE). The
binaries and the patch here are distributed under the same terms.
