<div align="center">
  <img src="icon.png" width="128" height="128" alt="Spid Launcher Icon" />
  <h1>Spid Launcher</h1>
  <p><strong>A sleek, modern, offline Minecraft launcher built with Electron for maximum performance.</strong></p>
</div>

<br/>

## 🚀 Overview

Spid Launcher is a fully-featured, ultra-fast custom Minecraft launcher designed to provide a seamless, modern experience for managing your Minecraft instances, mods, and performance settings. It bypasses clunky legacy systems to give you complete control over your game.

### 🌟 Key Features
- **Seamless Instance Management**: A fluid, highly responsive interface for creating and managing multiple Minecraft instances effortlessly.
- **Offline & Microsoft Accounts**: Play securely with your official Microsoft account, or easily add offline accounts for LAN/Cracked servers.
- **Max Performance Engine**: Automatically downloads and injects top-tier performance mods (Sodium, Lithium, Embeddium, etc.) for both Fabric and Forge based on your loader choice.
- **Aggressive JVM Tuning**: Ships with built-in Java garbage collection profiles (ZGC, G1GC, Shenandoah) and Tiered Compilation flags to squeeze out maximum FPS.
- **Modrinth Integration**: Browse, search, and install Modpacks, Mods, Resource Packs, and Shaders directly from the Modrinth API.
- **Discord Rich Presence**: Automatically updates your Discord status to show what you're playing and what mods you're browsing.

## 🛠️ Installation & Setup

If you want to run or build the launcher from the source code, you'll need [Node.js](https://nodejs.org/) installed on your machine.

1. **Clone or Download** this repository.
2. Open a terminal in the folder and install the dependencies:
   ```bash
   npm install
   ```
3. Start the launcher in development mode:
   ```bash
   npm start
   ```

## 📦 Building the `.exe`

Spid Launcher uses `electron-builder` to package the app into a clean Windows installer. 

> **Note for Windows Users:** You may need to run your terminal as an Administrator to successfully build the app locally, as `electron-builder` needs to create symbolic links.

To build the installer, simply run:
```bash
npm run build
```
Once finished, you will find `Spid Launcher Setup.exe` inside the `dist` folder!

## 🎮 The Performance Engine

Tired of lagging? The built-in **Performance Engine** does the heavy lifting for you. When the "Max FPS" preset is selected in the Settings menu, the launcher will:
- Pass highly aggressive `-XX` flags to Java (enabling compressed pointers, disabling explicit GC, and tuning the JIT compiler).
- Automatically download **Sodium, Lithium, and FerriteCore** if you launch a Fabric instance.
- Automatically download **Embeddium, Canary, and Pluto** if you launch a Forge or NeoForge instance.

## 📁 Project Structure
- `/src/main.js` - Electron backend, IPC handlers, game downloading, and process spawning.
- `/src/renderer/` - The frontend HTML/CSS/JS driving the beautiful user interface.
- `/src/jvm-config.js` - The brains behind the aggressive Java argument generation.
- `/src/download-manager.js` - A custom multi-threaded file downloader ensuring massive modpacks download fast and reliably.

## 📝 License
This project is for educational and personal use. Asset downloads are powered by the incredible Modrinth API. Minecraft is a trademark of Mojang Synergies AB.
