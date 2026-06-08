# STAR SHARE 🚀

STAR SHARE is a cross-platform, local network utility developed in Flutter. It allows you to instantly share files, directories, and chat messages between Android and Windows devices completely offline. It is built to work without any internet connection, relying purely on your local Wi-Fi or mobile hotspot.

---

## 🌟 Key Features

### 1. Zero-Configuration Auto-Discovery
STAR SHARE features an intelligent **TCP Subnet Scanner** that bypasses standard UDP broadcast limitations. It scans the local subnet dynamically, making it highly reliable even on strict enterprise Wi-Fi networks and Android Mobile Hotspots where UDP broadcasts are typically blocked.

### 2. Multi-File & Folder Support
Queue up multiple files or send entire directories in one go. The app recursively lists all files inside directories and transfers them sequentially.

### 3. Unified Local Chat Room
Chat in real-time with other active users on your local network:
* **Private Messages 🔒:** Encrypted using your 4-digit passcode. Only users with the same PIN can read them; otherwise, they appear masked as `****`.
* **Public Messages 👁️:** Viewable by everyone. If a user turns off public chat visibility in settings, public messages are masked with an Eye icon toggle to reveal them manually.

### 4. Standalone History Tab & Native Directory Launcher
* A clean transaction log displaying the time, file size, sender/receiver, and status.
* Includes an **Open Folder** button. In Windows, it launches File Explorer directly to your Downloads folder. In Android, it natively triggers the system File Manager.

### 5. Native Directories Integration
No scoped storage limitations. Received files are saved straight to:
* **Android:** `/storage/emulated/0/Download` (The system-wide public Downloads folder).
* **Windows:** Standard `Downloads` folder.

### 6. Localization & Themes
* Localized into 6 languages: **Persian, English, Arabic, Spanish, Chinese, and Japanese**, with real-time language switching.
* Full support for high-contrast **Light and Dark modes**.

### 7. Automated Update Checker
On startup, if internet is available, the app silently checks `https://raw.githubusercontent.com/ArefBahrami1996/StarShare/main/Ver.txt` on GitHub. If a newer version is found, it prompts the user with an intuitive modal containing a direct download link.

---

## 🛠️ Code Architecture

The project is structured following clean, modular principles to ensure readability, scalability, and easy maintenance:

```text
lib/
├── screens/
│   ├── about_screen.dart       # About page, developer info, QR share pop-up
│   ├── chat_screen.dart        # Chat room interface (public/private logic)
│   ├── history_screen.dart     # Detailed transfer log, native folder opener
│   ├── navigation_screen.dart  # Shell controller, update checker, central state
│   ├── settings_screen.dart    # Theme, language, and chat toggles
│   └── share_screen.dart       # Core file sharing and device scanning screen
├── main.dart                   # Application entry point, theme & localization listeners
├── network_manager.dart        # Core P2P engine (TCP server, auto-scanner, direct sockets)
└── translations.dart           # String maps for all supported languages
