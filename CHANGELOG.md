# Changelog

All notable changes to this project will be documented in this file.

## [1.0.5] - 2026-03-27

### Fixed
- **DRM Handling:** Prevented the script from saving corrupted/unplayable .mp4 files when the key server is offline. The script now safely skips these files. Because no broken file is saved, the script will naturally try to download them again the next time you sync that specific creator.
- **Dump Json:** Improved
- **New Site:**  Patreon integration so the file structure will change (next update)

--------------------------------------------
## [1.0.4] - 2026-03-13

### Fixed 
- **API Adaptation:** Updated the downloader to handle the recent OnlyFans API change. Photo post responses shifted from arrays to objects ({"list": [...]}); the script now correctly parses the new format to prevent skipped downloads.

⚠️⚠️ ***NEED DELETE OLD CACHE***⚠️⚠️

### Added 
- **Dynamic Text Watermark:** New feature to automatically apply a customizable watermark to photos. It auto-detects resolution to ensure perfect scaling and includes a subtle semi-transparent background for readability.
- **Custom Filename Prefix:** Added the ability to set a personalized prefix (e.g., @YourTag or any) for all downloaded files directly from the settings.
- **New Dependency:** Added `Pillow` (PIL) 
--------------------------------------------
## [1.0.3] - 2026-03-09

### Fixed
- **Chats DRM:** Fixed and now full supported

--------------------------------------------
## [1.0.2] - 2026-02-25

### Added
- **Chat DRM Support:** Added suppart for downloading DRM-protected media from direct messages. *(Note: This feature is currently untested as I haven't encountered DRM-protected chat content to fully verify it yet).*
- **External API Update:** Updated the external backend API to properly handle and route license requests for encrypted chat messages using the `/drm/message/` endpoint.

### Fixed
- **Completion Message Crash:** Fixed a `NameError` crash caused by a typo (`total_global_failes` -> `total_global_files`) that occurred when no new files needed downloading.
- **Debug Logging:** Fixed an issue where debug logging would silently fail.
- **DRM Race Condition:** Fixed a critical race condition during parallel DRM downloads.
