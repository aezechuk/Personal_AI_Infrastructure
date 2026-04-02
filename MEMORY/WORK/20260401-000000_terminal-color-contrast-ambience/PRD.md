---
task: Terminal color theme with contrast and ambience
slug: 20260401-000000_terminal-color-contrast-ambience
effort: standard
phase: learn
progress: 10/10
mode: interactive
started: 2026-04-01T00:00:00Z
updated: 2026-04-01T00:00:00Z
---

## Context

User wants to change Apple Terminal.app color theme. Current: "Basic" (light/white).
Goal: more contrast, more ambience, less white. User has astigmatism — avoid pure white foreground
(causes halation effect) and pure black background (too harsh). Use warm-toned dark theme.

Terminal: Apple Terminal.app (TERM_PROGRAM=Apple_Terminal). Shell: Fish + zsh (zshrc present).
Colors stored as NSKeyedArchiver-encoded NSColor binary plists in com.apple.terminal prefs.

### Risks
- Modifying Terminal prefs directly requires quitting and reopening Terminal to see effect
- NSColor plist encoding is complex — verified format from existing Homebrew profile
- Wrong color encoding silently breaks the profile

## Criteria

- [x] ISC-1: New terminal profile created in com.apple.terminal preferences
- [x] ISC-2: Background color is dark warm (not pure black, not white)
- [x] ISC-3: Foreground/text color is warm cream (not pure white, not gray)
- [x] ISC-4: Contrast ratio between bg and fg is high enough to read clearly
- [x] ISC-5: All 16 ANSI colors set with warm, atmospheric palette
- [x] ISC-6: Cursor color set (visible against dark bg)
- [x] ISC-7: Selection color set (visible highlight)
- [x] ISC-8: Profile set as default startup profile
- [x] ISC-9: Profile name is descriptive ("Gruvbox Dark")
- [x] ISC-A1: Basic (white) profile is NOT deleted — only new profile added

## Decisions

## Verification
