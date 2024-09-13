Cattr Desktop App
==========
Electron desktop application for Cattr

## Requirement
1. Node.js (>= v18)
2. yarn via `npm i -g yarn`

## Installation
1. Clone this repository
2. Install dependencies via `yarn`
3. Run webpack via `yarn build-watch` (or `yarn build-development` if you don't want to watch files for changes)
4. When build completes, run `yarn dev` to launch client in development mode

## Development mode
There are two major differences between development and production modes:
1. Automatical error reporting disabled in development mode.
2. Development installation uses different keychain service name and application folder path (with "-develop" suffix).

## Build
1. Ensure that all necessary dependencies are installed
2. Ensure that `package.json` and `src/base/config.js` contains right configuration
3. Build application in production mode via `yarn build-production`
4. Build executable for your favourite platform (output directory is /target).

## Upload Sentry sourcemaps
1. Copy `.sentry.main.example` to `.sentry.main`, then fill with configuration for Main process project.
2. Copy `.sentry.renderer.example` to `.sentry.renderer.example`, then fill with configuration for Renderer process project.
3. During release preparation, run `yarn build-release` to build & submit release files to Sentry.

How to build executable?
  - **macOS:** `yarn package-mac` will produce signed & notarized DMG
  - **Linux:** `yarn package-linux` will produce Tarball, DPKG and AppImage
  - **Windows:** `yarn package-windows` will produce installer and portable executables

Compatibility sheet:
  - **Host with macOS:** can produce builds only for macOS
  - **Host with Linux:** can produce builds for Linux and Windows (using Wine)
  - **Host with Windows:** can produce builds only for Windows
