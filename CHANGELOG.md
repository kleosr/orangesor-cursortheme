# Changelog

## [1.1.0] - 2026-05-17

### Fixed
- **CRITICAL**: Dark theme variable tokens were invisible (1.22:1 contrast ratio) - fixed to use visible warm beige
- **CRITICAL**: Dark theme comment colors were unreadable (33% alpha blend, ~1.26:1) - now uses solid accessible gray
- **CRITICAL**: Dark theme error color (#CF2D56) failed WCAG AA (3.71:1) - now meets 4.5:1 minimum
- **CRITICAL**: Dark theme success/green (#1F8A65) barely failed WCAG AA (4.35:1) - now meets threshold
- **CRITICAL**: Light theme accent (#F54E00) failed WCAG AA for normal text (3.28:1) - darker variant where needed
- **CRITICAL**: Light theme used blue (#2B6CB0) for all success/green semantics instead of green - fixed to use proper green
- **CRITICAL**: Light theme ANSI green was mapped to blue, ANSI cyan to orange - fixed semantic mapping
- **CRITICAL**: Light theme missing 29 color keys present in dark theme - added for parity
- **CRITICAL**: Light theme missing all bracket highlighting (editorBracketHighlight) - added
- **CRITICAL**: Light theme missing all scmGraph colors - added
- **CRITICAL**: Light theme missing errorLens extension colors - added
- **CRITICAL**: Extension icon was 2.1MB - compressed to 13.6KB
- **CRITICAL**: VSIX binary (2.3MB) was tracked in git - removed

### Changed
- Expanded syntax highlighting tokens from 10 to 30+ groups for proper language support
- Added markdown, diff, template literal, regexp, and operator token scopes
- Removed deprecated VS Code color keys (activityBarTop, paneComposite, paneCompositePart, sideBySideEditor)
- Fixed light theme ANSI color mapping for semantic correctness (green=green, cyan=cyan)
- Fixed extensionButton.prominentHoverBackground (was same as non-hover, no visual feedback)
- Fixed welcomePage.progress.foreground (was white on light background = invisible)
- Fixed textLink colors (were missing from light theme)
- Fixed editorCursor.background (was missing from light theme)
- Fixed light theme debug icon colors for consistency with orange accent
- Fixed light theme symbol icon colors for cross-theme consistency
- Fixed light theme charts.green (was blue) and charts.blue (was orange)
- Fixed gitDecoration.renamedResourceForeground for cross-theme consistency

### Added
- Syntax highlighting for 20+ new scopes: operators, punctuation, variables.language,
  constants, attributes, markdown, diffs, template interpolation, regex, invalid syntax
- WCAG AA contrast compliance for all critical text pairs
- Comprehensive scmGraph (Source Control Graph) colors in light theme
- textLink.foreground and textLink.activeForeground colors in both themes
- settings.modifiedItemIndicator and tab.unfocusedActiveForeground in light theme

### Improved
- README now uses local image paths instead of external URLs
- Fixed confusing README description (no longer conflicts Cursor/VS Code)
- Added VSIX manual installation instructions
- .vscodeignore now includes CHANGELOG.md in package
- .gitignore no longer tracks VSIX binary files

## [1.0.24] - 2024-12-24

### Changed
- Updated extension icon to new orange slice design

## [1.0.0] - 2024

### Added
- Initial release
- Cursor Dark theme
- Cursor Light theme
