# Trigger EstLint
Cross-platform command palette powered by Tauri (Rust + TypeScript). Compatible with Windows, macOS, and Linux.

**Note**: Flat workspace structure with all components at root level.

## Features
- Universal hotkey: `Alt+Shift+K` (all platforms)
- Background process with tray icon
- Borderless, translucent interface
- Built-in diagnostics (debug mode)

## Installation

### Prerequisites
- Node.js 20+ and yarn (dependency manager)
- Rust 1.75.0+ with Cargo
- System dependencies:
  - Windows: Edge WebView2
  - macOS: Command Line Developer Tools
  - Linux: libwebkit2gtk-4.0-dev, gcc, g++

### Setup and Launch
```bash
git clone https://github.com/chaos-labs/trigger-suite.git
cd trigger-suite
yarn setup

# Debug mode
yarn dev:app

# Release build
yarn build:app
```

## Usage
Application operates as background service with notification area icon.

- **Toggle**: `Alt+Shift+K` (all platforms)
- **Dismiss**: `Esc` key or focus loss
- **Tray Menu**: Right-click to toggle visibility or terminate

## Development

### Repository Layout
```
trigger-suite/
├── ui/                    # React interface
├── core/                  # Rust engine
├── shared/               # Common utilities
├── package.json          # Dependencies
└── workspace.yaml        # Workspace config
```

All commands run from root directory.

### Technology Foundation
- UI Layer: TypeScript + React + Vite + TailwindCSS
- Core Layer: Rust via Tauri
- Store: Zustand
- QA: Vitest + React Testing Library

### Available Commands
```bash
# Development
yarn dev:app           # Launch dev environment
yarn dev:ui            # UI only

# Production
yarn build:app         # Package application
yarn build:ui          # Compile UI

# Quality Assurance
yarn qa                # Execute test suite
yarn qa:report         # Coverage analysis
yarn qa:live           # Interactive mode

# Code Standards
yarn check:style       # Validate formatting
yarn fix:style         # Auto-correct issues
```

### Distribution Artifacts
```bash
yarn build:app
```

Platform bundles in `core/dist/bundle/`:
- Windows: `.msi` setup and standalone `.exe`
- macOS: `.dmg` image and `.app` package
- Linux: `.deb`, `.rpm` installers and `.AppImage` portable

## Configuration

### Keyboard Binding
Edit `core/bindings.rs`. Current: `Alt+Shift+K`

### Interface Properties
Adjust in `core/config.json`:
- Dimensions: 640x450 pixels
- Chrome-less with transparency
- Topmost layer, hidden from dock
- Initially invisible

## Contributing
1. Fork repository
2. Clone: `git clone https://github.com/your-handle/trigger-suite.git`
3. Setup workspace: `yarn setup`
4. Branch: `git checkout -b enhancement/description`
5. Implement and validate
6. Commit with message
7. Push changes
8. Submit Pull Request

Standards: ESLint + Prettier (TypeScript), rustfmt + clippy (Rust)

## License
GPL-3.0 License - refer to LICENSE document.
