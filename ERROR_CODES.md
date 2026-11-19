# LumaCam Error Codes

Format: `LC-<AREA>-<NNN>`. Each code has a meaning, a user-facing explanation, and a resolution. The iOS
(`LumaError.swift`) and Windows (`ErrorCatalog.cs`) catalogues must stay in sync with this table.

| Code | Area | Meaning | Resolution shown to user |
|---|---|---|---|
| LC-CAM-001 | Camera | Camera permission denied | Open Settings › LumaCam and allow Camera. |
| LC-CAM-002 | Camera | Microphone permission denied | Open Settings › LumaCam and allow Microphone, or use a Windows microphone. |
| LC-CAM-003 | Camera | No camera available | Close other apps using the camera, then retry. |
| LC-CAM-004 | Camera | Capture session failed to start | Restart LumaCam. If it persists, restart the iPhone. |
| LC-CAM-005 | Camera | Session interrupted (call, another app, multitasking) | Streaming resumes automatically when the interruption ends. |
| LC-CAM-006 | Camera | Requested format not supported | Choose a resolution/FPS from the list. |
| LC-CAM-007 | Camera | Device configuration lock failed | Retry; another process may hold the camera. |
| LC-CAM-008 | Camera | Thermal state critical, capture throttled | Let the iPhone cool down; LumaCam reduced the frame rate. |
| LC-CAM-009 | Camera | Battery critically low | Connect the iPhone to power. |
| LC-CAM-010 | Camera | Control not supported by active camera | The control is hidden for this lens. |
| LC-ENC-001 | Encoder | Failed to create H.264 encoder | Lower the resolution and retry. |
| LC-ENC-002 | Encoder | Encoding error | The stream restarts with a new keyframe automatically. |
| LC-NET-001 | Network | Wi-Fi unavailable | Connect the iPhone to the same Wi-Fi as the PC. |
| LC-NET-002 | Network | Studio unreachable | Check both devices share a network and the Windows firewall allows LumaCam Studio. |
| LC-NET-003 | Network | Local network permission denied | Open Settings › LumaCam and enable Local Network. |
| LC-NET-004 | Network | Connection lost | Reconnecting automatically. |
| LC-NET-005 | Network | TLS certificate mismatch | The PC's identity changed. Forget it and pair again. |
| LC-PAIR-001 | Pairing | Pairing code expired | Generate a new QR code in Studio. |
| LC-PAIR-002 | Pairing | Pairing code already used or invalid | Generate a new QR code in Studio. |
| LC-PAIR-003 | Pairing | Invalid QR code | Scan the QR code shown in LumaCam Studio. |
| LC-PAIR-004 | Pairing | Authentication failed (device unknown/revoked) | Pair again from Studio. |
| LC-PAIR-005 | Pairing | Too many attempts | Wait one minute and retry. |
| LC-PROTO-001 | Protocol | Malformed or oversized message | Update both apps to the same version. |
| LC-PROTO-002 | Protocol | Unsupported protocol version | Update both apps to the same version. |
| LC-DEC-001 | Decoder | Failed to create H.264 decoder | Update GPU drivers; LumaCam falls back to software decoding. |
| LC-DEC-002 | Decoder | Decoding error | A keyframe is requested automatically. |
| LC-VCAM-001 | Virtual camera | OS does not support MF virtual cameras | Windows 11 (build 22000+) is required. |
| LC-VCAM-002 | Virtual camera | Virtual camera setup failed | Settings › Virtual camera › Set up again, or use the installer. |
| LC-VCAM-003 | Virtual camera | Media source not registered (e.g. portable copy) | Settings › Virtual camera › Set up (one Windows permission prompt). |
| LC-VCAM-004 | Virtual camera | Frame shared memory unavailable | Restart LumaCam Studio. |
| LC-VCAM-005 | Virtual camera | Setup cancelled at the Windows permission prompt | Choose Set up again and select Yes. |
| LC-SYS-001 | System | Unsupported Windows version | Windows 10 1809+ for preview, Windows 11 for the virtual camera. |
