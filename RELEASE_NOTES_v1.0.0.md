# Storage Compare v1.0.0 — Initial macOS Release

We are excited to announce the first official release of **Storage Compare by Snaply**, a precision desktop application for offline duplicate detection, multi-drive comparison, and safe storage consolidation.

---

### 🚀 Highlights & Features

- **100% Offline & Zero Telemetry:** Complete privacy. No network calls, no analytics beacons, and no tracking. All hash calculations, file indexes, and databases remain strictly on your local disk.
- **Read-Only Scanning & Discovery:** Safe by design. Enumeration, comparison, and consolidation planning will never touch, rename, or modify your files.
- **Sequential Step-by-Step Scan:** Compare disconnected drives without needing to plug all your external hard drives and SSDs in at once.
- **Multi-Stage Telemetry Funnel:** Fast $O(1)$ size pruning, 8 KB chunk fingerprinting, and 64 KB chunk-streamed SHA-256 cryptographic hash verification.
- **Native macOS Finder Trash Integration:** Safe deletion via Apple’s native `FileManager.trashItem`, ensuring deleted duplicates can be recovered from the Trash.
- **Share App Feature:** Quick, one-click link sharing modal popup to share the official download link with colleagues and friends.
- **Built for Apple Silicon:** High-performance native Cocoa window wrapper with WebKit UI, optimized for macOS 11.0+ on Apple Silicon (M1/M2/M3/M4).

---

### 📦 Download Assets

| Asset | Platform / Architecture | Size | SHA-256 Checksum |
| :--- | :--- | :--- | :--- |
| **`Storage Compare.dmg`** | macOS (Apple Silicon `arm64`) | ~11.3 MB | `b8991d1890e28cf38181988a789189fdc8f57db3917b16130c1e33d1d5f15015` |

---

### 📋 Installation & First-Launch (macOS Gatekeeper)

1. Download **`Storage Compare.dmg`** from the release assets below.
2. Double-click the `.dmg` file to mount it.
3. Drag the **Storage Compare** icon into the **Applications** folder shortcut.
4. **First Launch Note:** Because this release is independently distributed and ad-hoc signed:
   - **Right-click (or Control-click)** the Storage Compare app in Applications.
   - Choose **Open**, and click **Open** in the confirmation prompt.
   - (Or go to **System Settings > Privacy & Security** and select **Open Anyway**).
5. Accept the First-Run Legal Agreement & Zero-Telemetry Privacy Policy to start using the app.

---

### 💡 License & Distribution Policy

Storage Compare is **proprietary freeware**. You are free to download and use the application free of charge for personal and internal business use. You may also transfer this official, unmodified installer to others (including via direct file transfer or USB drive) at no cost.
