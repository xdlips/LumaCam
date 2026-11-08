# Troubleshooting

Every error shows a code (`LC-…`). The full list with resolutions is in
[shared/Protocol/ErrorCodes.md](ERROR_CODES.md).

| Symptom | Fix |
|---|---|
| iPhone can't find the PC | Both devices must be on the same network; guest Wi-Fi usually isolates clients. Check iOS Settings › LumaCam › Local Network. |
| `LC-NET-002` Studio unreachable | Allow LumaCam Studio through Windows Firewall on **Private** networks, and make sure Windows classifies your network as Private. |
| `LC-PAIR-001/002` | QR codes last 2 minutes and work once. Generate a new one. |
| `LC-NET-005` PC identity changed | Studio's certificate was regenerated (reinstall or profile reset). Forget the PC on the iPhone and pair again. |
| Stream pauses | iOS stops the camera when LumaCam leaves the screen. Keep LumaCam open; it keeps the display awake. |
| Choppy video | Lower the quality preset or resolution. 5 GHz Wi-Fi helps a lot. Watch "Dropped" in the status bar. |
| Virtual camera missing | Windows 11 is required (`LC-VCAM-001`). Run `install.ps1` elevated, then `LumaCam.VCamCheck.exe`. |
| Virtual camera shows black | That's the no-signal state: no iPhone is connected to Studio, or Studio is closed. |

## Collecting diagnostics
- iOS: `xcrun devicectl device copy from --device <id> --domain-type appDataContainer --domain-identifier com.ozgurdivarci.lumacam --source Library/Logs/lumacam.log --destination .`
- Windows: Studio › Settings › Open Log Folder.
