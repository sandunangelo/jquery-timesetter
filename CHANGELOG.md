# Changelog

All notable changes to this project will be documented in this file.

## [1.1.0] - 2025-09-05

### Added
- Added package.json for better dependency management
- Added comprehensive test file (test-jquery-upgrade.html) to verify jQuery 3.x compatibility
- Added Bootstrap Icons 1.11.3 for modern icon support
- Added comprehensive Bootstrap 5 compatibility test file (test-bootstrap-upgrade.html)

### Changed
- **BREAKING**: Upgraded jQuery dependency from 2.2.4 to 3.7.1
- **BREAKING**: Upgraded Bootstrap dependency from 3.3.7 to 5.3.3
- **BREAKING**: Replaced deprecated Glyphicons with Bootstrap Icons
  - `glyphicon-triangle-top` → `bi bi-triangle-fill`
  - `glyphicon-triangle-bottom` → `bi bi-triangle-fill` (rotated 180°)
- Updated all deprecated jQuery methods for compatibility with jQuery 3.x:
  - Replaced `.bind()` with `.on()`
  - Replaced `.unbind()` with `.off()`
- Updated all Bootstrap CDN references to use jsDelivr (more reliable)
- Updated CSS, LESS, and minified CSS files with new Bootstrap imports
- Updated package.json to include Bootstrap and Bootstrap Icons dependencies
- Updated dependency references in all plugin files
- Updated README.md to reflect new jQuery version requirement

### Improved
- Better future compatibility with modern jQuery versions
- More maintainable code structure with package.json
- Modern, responsive design with Bootstrap 5.3.3
- Better icon rendering with Bootstrap Icons
- Improved visual consistency with current web standards
- Better mobile responsiveness

### Technical Notes
- The plugin now uses jQuery 3.7.1 (latest stable version as of 2025-09-05)
- Bootstrap 5 uses different class naming conventions but the plugin remains compatible
- Icons are now served via Bootstrap Icons instead of deprecated Glyphicons
- All existing functionality remains the same - only internal method calls were updated
- Backward compatibility: Projects using older jQuery versions should update to jQuery 3.x

## [1.0.0] - 2016-11-26

### Initial Release
- jQuery Timesetter plugin with hour/minute input controls
- Bootstrap 3.3.7 integration
- Keyboard arrow key support
- Real-time validation
- jQuery 2.2.4 compatibility
