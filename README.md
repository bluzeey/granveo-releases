# Granveo Releases

This is the public releases repository for Granveo Desktop - a personal knowledge graph application.

**Note:** This repository contains only compiled binaries and release artifacts. Source code is private.

## Download Granveo Desktop

Visit the [Releases page](https://github.com/bluzeey/granveo-releases/releases/latest) to download the latest version.

## Available Downloads

### macOS
- **Apple Silicon (M1/M2/M3/M4)**: `granveo-desktop-mac-arm64.dmg`
- **Intel Macs**: `granveo-desktop-mac-x64.dmg`

### Windows
- **Windows 10/11 (64-bit)**: `granveo-desktop-windows-x64.exe`

### Linux
- **Linux (AppImage)**: `granveo-desktop-linux.AppImage`
- **Linux (Debian/Ubuntu)**: `granveo-desktop-linux.deb`

## Release Naming Convention

All releases follow this naming pattern:
```
granveo-desktop-v{VERSION}-{PLATFORM}-{ARCH}.{EXT}
```

Examples:
- `granveo-desktop-v1.0.0-mac-arm64.dmg`
- `granveo-desktop-v1.0.0-windows-x64.exe`
- `granveo-desktop-v1.0.0-linux.AppImage`

## System Requirements

### macOS
- macOS 11.0 (Big Sur) or later
- 4GB RAM minimum, 8GB recommended
- 200MB free disk space

### Windows
- Windows 10 (version 1903) or later / Windows 11
- 4GB RAM minimum, 8GB recommended
- 200MB free disk space

### Linux
- Ubuntu 20.04+, Fedora 34+, or equivalent
- 4GB RAM minimum, 8GB recommended
- 200MB free disk space

## Installation

### macOS
1. Download the `.dmg` file for your architecture
2. Open the `.dmg` file
3. Drag "Granveo" to your Applications folder
4. Launch from Applications

**Note:** macOS may warn about an unidentified developer. Right-click the app and select "Open" to proceed.

**Troubleshooting "App is damaged" error:**
If macOS shows "Granveo is damaged and can't be opened" (common for unsigned apps), run this in Terminal:
```bash
xattr -dr com.apple.quarantine "/Applications/Granveo.app"
```
Then open Granveo again.

### Windows
1. Download the `.exe` installer
2. Run the installer
3. Follow the installation wizard
4. Launch from Start menu or Desktop shortcut

### Linux (AppImage)
1. Download the `.AppImage` file
2. Make it executable: `chmod +x granveo-desktop-linux.AppImage`
3. Run: `./granveo-desktop-linux.AppImage`

### Linux (Debian/Ubuntu)
1. Download the `.deb` file
2. Install: `sudo dpkg -i granveo-desktop-linux.deb`
3. Fix dependencies: `sudo apt-get install -f`
4. Launch from applications menu

## API for Website Integration

To fetch the latest release programmatically:

```bash
curl -s https://api.github.com/repos/bluzeey/granveo-releases/releases/latest | jq '.assets[] | {name, browser_download_url}'
```

Response format:
```json
{
  "tag_name": "v1.0.0",
  "assets": [
    {
      "name": "granveo-desktop-mac-arm64.dmg",
      "browser_download_url": "https://github.com/bluzeey/granveo-releases/releases/download/v1.0.0/granveo-desktop-mac-arm64.dmg"
    },
    {
      "name": "granveo-desktop-mac-x64.dmg",
      "browser_download_url": "https://github.com/bluzeey/granveo-releases/releases/download/v1.0.0/granveo-desktop-mac-x64.dmg"
    },
    {
      "name": "granveo-desktop-windows-x64.exe",
      "browser_download_url": "https://github.com/bluzeey/granveo-releases/releases/download/v1.0.0/granveo-desktop-windows-x64.exe"
    },
    {
      "name": "granveo-desktop-linux.AppImage",
      "browser_download_url": "https://github.com/bluzeey/granveo-releases/releases/download/v1.0.0/granveo-desktop-linux.AppImage"
    }
  ]
}
```

## Release Automation

This repository receives binaries from the private source repository via GitHub Actions.

### For Maintainers

To publish a new release:

1. Build binaries in the source repository
2. Create a new release in this public repository
3. Upload the platform-specific binaries
4. Update the release notes with changelog

## Support

For issues, feature requests, or questions:
- Visit: https://granveo.com
- Email: support@granveo.com

## License

Granveo Desktop is proprietary software. All rights reserved.

© 2026 Granveo. All rights reserved.
