# Contributing to Compact Better Thermostat Card

Thank you for your interest in contributing! This document explains how to contribute and how releases are managed.

## Development Setup

1. Clone the repository
2. Copy `compact-better-thermostat-card.js` to your Home Assistant `config/www/` folder
3. Add the resource to your Lovelace configuration
4. Make changes and refresh your browser to test

## Code Style

- Use vanilla JavaScript (ES6+)
- No build tools or TypeScript
- Follow existing code patterns
- Add JSDoc comments for functions
- Use Home Assistant CSS variables for theming

## Submitting Changes

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/my-feature`)
3. Make your changes
4. Test thoroughly in Home Assistant
5. Commit with clear messages
6. Push to your fork
7. Open a Pull Request

## Versioning

This project follows [Semantic Versioning](https://semver.org/):

- **MAJOR** (x.0.0): Breaking changes
- **MINOR** (0.x.0): New features, backward compatible
- **PATCH** (0.0.x): Bug fixes, backward compatible

## Creating a Release

HACS uses GitHub Releases to detect new versions. Follow these steps:

### 1. Update Version Numbers

Update the version in `compact-better-thermostat-card.js`:

```javascript
const CARD_VERSION = 'x.y.z';
```

Also update the `@version` tag in the file header.

### 2. Update CHANGELOG.md

Add a new section at the top:

```markdown
## [x.y.z] - YYYY-MM-DD

### Added
- New features...

### Changed
- Changes...

### Fixed
- Bug fixes...
```

### 3. Commit Changes

```bash
git add .
git commit -m "Bump version to x.y.z"
git push
```

### 4. Create GitHub Release

1. Go to the repository on GitHub
2. Click "Releases" → "Create a new release"
3. Create a new tag: `vx.y.z` (e.g., `v1.3.0`)
4. Set release title: `vx.y.z`
5. Copy the relevant CHANGELOG section to the description
6. Click "Publish release"

### 5. HACS Update

HACS will automatically detect the new release. Users will see an update notification.

## Release Checklist

- [ ] Version updated in `compact-better-thermostat-card.js` (both `CARD_VERSION` and `@version`)
- [ ] CHANGELOG.md updated with new version section
- [ ] All changes tested in Home Assistant
- [ ] Changes committed and pushed
- [ ] GitHub Release created with tag `vx.y.z`
- [ ] Release notes include changelog entries

## File Structure

```
├── compact-better-thermostat-card.js  # Main card file
├── hacs.json                          # HACS configuration
├── README.md                          # User documentation
├── CHANGELOG.md                       # Version history
├── CONTRIBUTING.md                    # This file
└── LICENSE                            # MIT License
```

## HACS Configuration

The `hacs.json` file configures how HACS handles this repository:

```json
{
  "name": "Compact Better Thermostat Card",
  "content_in_root": true,
  "filename": "compact-better-thermostat-card.js",
  "render_readme": true,
  "homeassistant": "2023.0.0"
}
```

- `content_in_root`: The JS file is in the repository root (not in `dist/`)
- `filename`: The main file HACS should download
- `render_readme`: Use README.md for the HACS info page
- `homeassistant`: Minimum Home Assistant version required

## Questions?

Open an issue on GitHub if you have questions or need help.
