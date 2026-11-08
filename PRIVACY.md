# Privacy

LumaCam is local-first. This page describes what the software does with your data.

- **Video** goes directly from the iPhone to your PC over your local network (or USB, in a later release). It
  is encrypted with TLS, and the PC's certificate is pinned during QR pairing. It never passes through any server.
- **No recording.** Neither app writes video to disk. (The developer-only `DevReceiver` tool writes a file only
  when explicitly passed `--out`.)
- **No accounts, no analytics, no telemetry, no cloud services.**
- **Update check (optional, on by default):** Studio (every 12 h) and the iPhone app (once a day) send one anonymous
  HTTPS request to `api.github.com/repos/xdlips/LumaCam/releases` to see whether a newer version exists. The request
  contains only the app name and version in the User-Agent: no device ID, no account, no usage data. Downloaded
  installers are verified against the release's SHA-256 checksums before they run. Turn it off in Settings → Updates.
- **Pairing secrets:** each iPhone gets a random 32-byte key. On iOS it's stored in the Keychain
  (this device only, never synced). On Windows it's encrypted with DPAPI for the current user. QR codes contain
  only a 2-minute single-use token, never a long-term secret.
- **Logs** record connection events and error codes. They never contain tokens, keys or video data.
  - iOS: `Library/Logs/lumacam.log` (in the app sandbox, rotated at 512 KB).
  - Windows: `%LOCALAPPDATA%\LumaCam\Logs` (7 days kept).
- **Network exposure:** Studio accepts connections only from private, link-local and loopback addresses, and the
  installer's firewall rule is limited to the Private profile. Unauthenticated peers can do nothing but attempt
  pairing (with a valid one-time token) or authentication, both rate-limited.

## Permissions
| Platform | Permission | Why |
|---|---|---|
| iOS | Camera | Capture video to stream to your PC. |
| iOS | Local Network | Find LumaCam Studio (Bonjour) and connect to it. |
| Windows | Firewall (Private networks) | Accept the iPhone's connection. |
| Windows | Internet (optional) | Anonymous update check against GitHub Releases. |
| Windows | Administrator (install only) | Register the virtual camera media source for the Windows Frame Server. |
