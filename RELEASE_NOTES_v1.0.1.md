# Storage Compare v1.0.1 — Data Management & Ephemeral Storage Release

Storage Compare **v1.0.1** introduces critical database optimization, default session-only ephemeral comparison, opt-in persistent incremental hashing, per-source session retention, tiered app-data management, interactive storage removal options, and an official macOS safe uninstaller tool.

The previous **v1.0.0** release remains fully accessible on our Releases page. Users upgrading from v1.0.0 can simply replace `/Applications/Storage Compare.app` or use the new uninstaller tool if a clean slate is preferred.

---

### 🚀 What's New & Improved in v1.0.1

1. **Default Temporary Session-Only Comparison**:
   - For fresh installations, comparison data (`file_records`, `duplicate_groups`, `scan_sessions`, `scan_errors`, temporary hash cache) is ephemeral by default.
   - Users can scan multiple drives or folders one at a time and compare them within the same running application session.
   - Upon normal application exit, temporary comparison records are wiped and the SQLite database is automatically compacted with `VACUUM` down to its baseline (~100 KB).
   - On startup, the application detects and cleans up any abandoned temporary comparison data left by a prior crash or force-quit.
   - **Zero Risk to Personal Data:** Original scanned files and folders on your computer and external drives are **never deleted or modified**. Verified backup manifests and deletion audit logs are permanently preserved.

2. **Opt-In Persistent Incremental Hashing**:
   - Users who regularly rescan large archives can enable **Persistent Incremental Hashing** under **⚙️ Storage -> Comparison Storage Mode**.
   - When enabled, hashes and metadata are retained across application restarts for near-instant repeat scans.
   - Shows the live size of the persistent cache and provides explicit one-click actions to clear the cache or purge stored source indexes at any time.

3. **Per-Source Session Retention (Multi-Drive Protection)**:
   - Automated scan session pruning (`keep_latest=2`) now operates strictly **per storage target / mount set**.
   - Scanning Drive B multiple times will **never** prune or discard the only scan session of an offline or unmounted Drive A.

4. **In-App Data & Storage Management Modal (Storage Settings)**:
   - Added a dedicated **Storage Settings** modal accessible directly from the **Storage & Transparency** card on the main dashboard.
   - Live dashboard displays local database disk size, total indexed files, cached cryptographic hashes, active storage mode, and free list pages.
   - Three tiered cleanup options:
     - **1. Clear Fingerprint & Hash Cache:** Purges cached cryptographic hashes and compacts the database while preserving drive sources and scan results.
     - **2. Clear Scan History & Indexes:** Purges historical scan sessions and duplicate matches while preserving drive configurations and legal agreements.
     - **3. Reset All App Data:** Resets the local database to a clean, minimal initial state without touching personal files.

5. **Interactive Storage Source Removal (Red Cross ✕)**:
   - Enhanced the red-cross (`✕`) folder button on storage cards with a dedicated interactive modal.
   - Users now have an explicit choice:
     - **Remove & Purge Cached Index (Reclaim Space):** Purges indexed file records and cached hashes from the local database and runs `VACUUM` immediately.
     - **Remove from Active View Only (Preserve Offline Index):** Hides the folder card from active scans while preserving historical comparison and consolidation metadata offline.
   - Includes clear confirmation that original files and folders are **never touched**.

6. **Official macOS Safe Uninstaller**:
   - Bundled standalone uninstaller (`uninstall_mac.sh` and double-clickable `Uninstall Storage Compare.command`) directly inside the DMG installer.
   - Checks for running processes, calculates reclaimable disk space, and safely deletes application-owned files:
     - `/Applications/Storage Compare.app` (optional user prompt)
     - `~/Library/Application Support/Storage Compare`
     - `~/Library/Caches/Storage Compare` & `~/Library/Caches/com.snaply.storagecompare`
     - `~/Library/Preferences/com.snaply.storagecompare.plist`
     - `~/Library/Saved Application State/com.snaply.storagecompare.savedState`
     - `~/Library/WebKit/com.snaply.storagecompare`
   - Strictly validates all paths before removal and guarantees **zero user documents, photos, or external drives are modified**. Supports dry-run inspection mode (`--inspect`).

---

### 📦 Download Assets

| Asset | Platform / Architecture | Size | SHA-256 Checksum |
| :--- | :--- | :--- | :--- |
| **`Storage Compare.dmg`** | macOS (Apple Silicon `arm64`) | 11.2 MB (11,774,305 bytes) | `52871a10b7c599e2765fed418034c8ae031ada86ca360bc3525b00bd7c14282a` |

---

### 📋 Installation & Upgrade Notes

1. Download **`Storage Compare.dmg`** from the release assets below.
2. Double-click the `.dmg` file to mount it.
3. Drag **Storage Compare** into the **Applications** shortcut icon (choose **Replace** if upgrading from v1.0.0).
4. **First Launch Note:** If macOS Gatekeeper displays an ad-hoc security notice:
   - **Right-click (or Control-click)** Storage Compare in Applications.
   - Choose **Open**, and click **Open** in the confirmation dialog.
5. Review the **Storage & Transparency** card on the dashboard or open **Storage Settings** to inspect or configure comparison storage mode anytime.

---

### 💡 License & Distribution Policy

Storage Compare is **proprietary freeware**. It is free to download and use for personal and internal business purposes. Official, unmodified installers may be transferred directly to others at no cost.
