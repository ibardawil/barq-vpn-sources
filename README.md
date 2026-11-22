# Barq VPN corresponding source

Barq VPN for Android (package `free.vpn`) includes open-source native components under the GPL-2.0, LGPL-3.0 and
MPL-2.0 licences. Each app release has a GitHub release here with the complete corresponding source of those components:

- strongSwan 6.1.0 and its Android bridge (IKEv2/IPsec), with Barq's patches applied and also kept as diffs
- OpenVPN (ics-openvpn fork) with its build files, OpenSSL, LZO and LZ4, with Barq's change applied and kept as a diff
- the Xray bridge and every Go module it links (Xray-core, REALITY and others), vendored from the hashes in `go.sum`
- the CMake, Gradle and shell files that build them, and the licence texts the app shows

Releases are tagged `v<versionName>-code<versionCode>`, matching the "Source code" link in the app under
Settings > Open-source licences. Each release carries one archive, `barq-vpn-sources-<version>-code<code>.tar.gz`, and
its `.sha256` file. Inside it:

- `README.txt`: the source commit and how to rebuild each native library
- `MANIFEST.tsv`: every component with its version, licence and path
- `SHA256SUMS`: the SHA-256 of every file in the archive

Barq's Kotlin application code is not part of these archives. It runs in the app process and talks to these libraries
through JNI, and to the OpenVPN and Xray executables through local sockets.

This repository contains no application code, signing material, configuration or server details.
