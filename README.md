# Accessible Persona Card – Carol (Low Vision)

A semantic, accessible user persona card focused on Carol, an older adult with low vision (macular degeneration). The page demonstrates practical accessibility patterns for low-vision users, aligned with WCAG 2.2.

## Quick start
- Open `index.html` in a desktop or mobile browser. No build tools or dependencies are required.

## What’s inside
`index.html` includes:
- Semantic HTML with a main region and headings for easy navigation.
- Skip link: “Skip to main content” appears on focus and jumps to the main content.
- Basic responsive layout and readable defaults (system fonts, comfortable spacing).
- Visible focus outlines and a prefers-reduced-motion media query.
- Language selector (English/Español) with reasonable defaults and ARIA states.
- Screen reader announcements via a polite live region for status messages.
- “Read Card Aloud” button powered by the Web Speech API (text-to-speech).

### Persona content
- Name: “Carol – Grandmother with Macular Degeneration”
- About: Background and daily use of the computer for email, reading, and simple shopping.
- Technologies and preferences: Browser zoom, high-contrast preference, larger click targets.
- Main barriers: Small text, low contrast, reflow issues at high zoom, small targets, inconsistent zoom behavior.
- WCAG 2.2 mapping: Contrast, Resize Text, Reflow, Text Spacing, Target Size (Minimum/AAA), Visual Presentation.
- Design recommendations: High contrast, 200%/400% zoom support, reflow, larger targets, spacing, relative units, color-independence, testing at high zoom.

## Accessibility details
- Keyboard
	- Skip link appears on focus; tab into the page to reveal it.
	- All interactive controls are reachable and show a clear focus style.
- Semantics
	- Structural landmarks and heading hierarchy support quick navigation for screen reader users.
- Low-vision support
	- Layout scales cleanly; text size and spacing are comfortable by default; styles avoid tiny targets.
	- CSS includes visible focus indicators and supports reduced motion.
- Announcements
	- A polite live region announces language changes and page load events.
- Text-to-speech
	- The “Read Card Aloud” button uses the browser’s SpeechSynthesis API (where supported) to read the page content.

## Known limitations and next steps
- Language toggle
	- Currently updates the skip link, name, and subtitle. Consider internationalizing all section headings and list content.
	- Externalize strings into a translations object for complete parity (EN/ES) and ensure the document `<html lang>` reflects the active language.
- Title consistency
	- The document `<title>` may not match the visible persona name. Align `<title>` with the current persona (“Carol”) for consistency and better assistive tech output.
- Styling
	- Inline CSS is fine for a demo; consider moving it to `styles.css` and adding high-contrast and dark-mode themes.
- Testing
	- Add automated accessibility checks (e.g., Axe) and a quick Playwright script to validate tab order and focus.
- Contrast verification
	- Validate color contrast (especially text on backgrounds) to meet WCAG 2.2 criteria (4.5:1 for normal text, 3:1 for large text).

## How to validate accessibility
1. Keyboard-only
	 - Reload the page; press Tab to focus the skip link; press Enter to jump to the main content.
	 - Continue tabbing to ensure all interactive items receive a visible focus and are reachable.
2. Zoom and reflow
	 - Zoom to 200% and 400% and confirm content remains usable without horizontal scrolling.
3. Screen reader
	 - Try NVDA/JAWS/VoiceOver to verify heading navigation and that language changes are announced.
4. Automated audits
	 - Run Lighthouse, WAVE, or Axe to check for critical issues.

## Project structure
```
accesible-persona-card/
├── index.html
└── README.md
```

