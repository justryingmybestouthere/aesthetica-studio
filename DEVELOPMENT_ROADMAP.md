# Aesthetica Studio — 10-Phase Development Roadmap

A complete, incremental plan for building a professional browser-based visual design application focused on CSS artistry, SVG, and creative experimentation.

---

## PHASE 1: Foundation & Core Canvas (Current)

**Duration:** 1–2 weeks  
**Focus:** Establish the application skeleton, basic editing, and local persistence.

### Goals

- [x] Professional studio-style UI layout (panels, topbar, statusbar)
- [x] Working canvas with 8 basic element types
- [x] Drag-and-drop, resize, rotate element interactions
- [x] Layer panel with visibility, selection, reordering
- [x] Basic properties panel (position, size, opacity)
- [x] Local project save/load via localStorage
- [x] Project export as JSON
- [x] Undo/redo foundation (history stack)
- [x] Keyboard shortcuts (Delete, Ctrl+D, Ctrl+S)
- [x] Code panel (HTML/CSS/JSON tabs, read-only)
- [x] AI drawer UI (closed state, messaging structure)
- [x] Responsive preview mode toggle
- [x] Toast notifications

### Deliverables

- Working editor with draggable elements
- Local project persistence
- Basic project management (New, Save, Export)
- Studio-style dark theme applied

### Technical Notes

- Use localStorage for MVP (no backend)
- All element data stored in structured JSON project model
- Canvas rendered as absolutely-positioned DOM elements
- Event handling: pointer events for drag/resize
- Single-file main.js (refactor in Phase 3)

---

## PHASE 2: Advanced Styling & CSS Laboratory

**Duration:** 2–3 weeks  
**Focus:** Transform basic styling into a powerful CSS experimentation tool.

### Goals

- [ ] **Color System**
  - Hex, RGB, HSL, OKLCH input modes
  - Color picker with eyedropper
  - Saved color palettes
  - Gradient editor (linear, radial, conic)
  - Gradient stops, angles, presets

- [ ] **Border & Shadow**
  - Individual corner radius control
  - Multiple box-shadow support (add/remove)
  - Inner shadow toggle
  - Border style selector (solid, dashed, dotted, etc.)
  - Gradient borders via SVG filters (advanced)

- [ ] **Filters & Effects**
  - Blur, brightness, contrast, grayscale, hue-rotate
  - Invert, saturate, sepia, drop-shadow
  - Multiple filters with individual sliders
  - Filter preview with real-time update

- [ ] **Background Modes**
  - Solid color
  - Gradients
  - Image upload
  - Pattern selector (optional)
  - Background size/position controls
  - Blend modes (multiply, screen, overlay, etc.)

- [ ] **Typography Controls**
  - Font family selector (system + Google Fonts)
  - Font size, weight, line-height
  - Letter spacing, word spacing
  - Text transform (uppercase, lowercase, capitalize)
  - Text shadow with multiple shadows
  - Text stroke (via filter or SVG)
  - Text gradient (via background-clip)
  - Text alignment, direction

- [ ] **Effect Presets**
  - Glassmorphism preset (blur + semi-transparent)
  - Neon glow preset
  - Soft glow preset
  - Y2K chrome preset
  - Holographic preset
  - Each preset is editable, not baked

- [ ] **Properties Panel Expansion**
  - Collapsible sections (Appearance, Shadow, Filters, etc.)
  - Smooth transitions between states
  - Real-time canvas preview

### Deliverables

- Advanced CSS properties UI
- 15+ built-in effect presets
- Color/gradient system
- Editable typography controls

### Technical Notes

- Create `StyleEditor` module to manage all CSS
- Generate valid CSS from all property changes
- Validate inputs (color values, numbers, etc.)
- Update code panel in real-time as styles change

---

## PHASE 3: Architecture Refactoring & Module System

**Duration:** 1–2 weeks  
**Focus:** Organize code into maintainable modules before adding complex features.

### Goals

- [ ] **File Structure**
  ```
  src/
  ├── main.js                  (app entry, initialization)
  ├── state.js                 (state management, project data)
  ├── history.js               (undo/redo system)
  ├── canvas/
  │   ├── renderer.js          (DOM rendering)
  │   ├── selection.js         (selection & interaction)
  │   ├── dragging.js          (drag/resize/rotate logic)
  │   └── grid.js              (snap, guides, alignment)
  ├── editor/
  │   ├── properties.js        (properties panel UI)
  │   ├── layers.js            (layer panel UI & logic)
  │   ├── library.js           (element insertion)
  │   └── toolbar.js           (canvas toolbar)
  ├── project/
  │   ├── save.js              (persistence logic)
  │   ├── export.js            (HTML/CSS/JSON export)
  │   ├── import.js            (project/HTML import)
  │   └── templates.js         (starter templates)
  ├── design/
  │   ├── css-generator.js     (CSS from properties)
  │   ├── element-factory.js   (element creation)
  │   └── effects.js           (effect presets)
  ├── ui/
  │   ├── panels.js            (panel management)
  │   ├── modals.js            (dialog system)
  │   ├── theme.js             (theme switching)
  │   └── shortcuts.js         (keyboard shortcuts)
  ├── ai/
  │   ├── chat.js              (AI drawer logic)
  │   ├── api.js               (AI provider abstraction)
  │   └── actions.js           (design actions)
  └── styles.css
  ```

- [ ] **State Management**
  - Centralized project state
  - Event emitter for state changes
  - Clear action creators
  - History/undo tied to actions

- [ ] **Module Exports**
  - Clear public APIs
  - No circular dependencies
  - Lazy-load where appropriate

- [ ] **Testing Structure**
  - Unit tests for pure functions (CSS generation, etc.)
  - Integration tests for workflows
  - Jest + DOM testing library setup

### Deliverables

- Clean, modular codebase
- Easier to add features
- Better performance (lazy-loaded modules)

### Technical Notes

- Use ES modules throughout
- Create an event bus for cross-module communication
- Maintain backward compatibility with Phase 1 projects
- Refactor existing functionality into modules

---

## PHASE 4: SVG Studio & Paths

**Duration:** 2–3 weeks  
**Focus:** Make SVG a first-class design tool, not just an element type.

### Goals

- [ ] **SVG Element Type**
  - Dedicated SVG element type
  - Inline SVG source editor
  - Live preview
  - Sanitization (remove scripts, validate)

- [ ] **SVG Shapes**
  - Circle, rectangle, polygon, star
  - Create from toolbar
  - Drag onto canvas
  - Individual fill/stroke controls

- [ ] **Path Editor**
  - Point-and-click path creation
  - Bezier curve handles
  - Smooth/sharp node modes
  - Add/remove/move points
  - Visual feedback

- [ ] **SVG Styling**
  - Fill color (solid, gradient, pattern)
  - Stroke color, width, style
  - Opacity, blend modes
  - Filters applied to SVG

- [ ] **SVG Transforms**
  - Rotate, scale, skew
  - Transform origin
  - Preserve aspect ratio

- [ ] **SVG Library**
  - 50+ built-in SVG icons
  - Customizable colors
  - Resizable
  - Searchable

- [ ] **SVG Source Editor**
  - Paste raw SVG
  - Edit XML directly
  - Live preview
  - Validate markup

### Deliverables

- Functional SVG editor
- 50+ icon library
- Path drawing tool
- SVG-to-element conversion

### Technical Notes

- Use DOMParser/XMLSerializer for SVG manipulation
- Create `SVGElement` class extending base Element
- Integrate Bezier libraries if needed (optional)
- SVG sanitization library (DOMPurify or similar)
- Store SVG as string in element.content

---

## PHASE 5: Animation & Timeline

**Duration:** 2–3 weeks  
**Focus:** Enable motion design and keyframe-based animation.

### Goals

- [ ] **Animation Presets**
  - Float, bounce, pulse, rotate, wiggle, shimmer
  - Fade in/out, slide, scale, glow
  - Path follow (advanced)
  - Each preset generates CSS @keyframes

- [ ] **Animation Inspector**
  - Duration slider (0–10s)
  - Delay slider
  - Easing function selector (ease-in, ease-out, cubic-bezier, etc.)
  - Iteration count (1, 2, infinite)
  - Direction (normal, reverse, alternate)
  - Fill mode (none, forwards, backwards)

- [ ] **Simple Timeline**
  - Visual timeline representation
  - Show animations staggered in time
  - Click to edit animation properties
  - Play/pause preview
  - Timeline scrubber

- [ ] **Keyframe Editor** (Basic)
  - For advanced animations, define keyframes manually
  - Percentage-based stops (0%, 25%, 50%, etc.)
  - Modify properties at each keyframe
  - Add/remove keyframes

- [ ] **Animation Preview**
  - Play animations in the canvas
  - Loop/single play toggle
  - Speed control
  - Reset/restart

- [ ] **Export**
  - Generated CSS animations in exported code
  - No external libraries required

### Deliverables

- 15+ animation presets
- Working timeline UI
- Keyframe editor
- Export with valid CSS animations

### Technical Notes

- Store animations in element.animations array
- Generate CSS @keyframes at export time
- Use requestAnimationFrame for preview
- Animation data format:
  ```js
  {
    name: "bounce",
    duration: 1,
    delay: 0,
    easing: "ease-in-out",
    iterationCount: "infinite",
    direction: "normal"
  }
  ```

---

## PHASE 6: Templates, Themes & Presets

**Duration:** 1–2 weeks  
**Focus:** Accelerate design creation with high-quality starter templates.

### Goals

- [ ] **Template System**
  - 20+ starter templates (Dreamy Profile, Ocean, Y2K, etc.)
  - Each template is a complete project
  - Preview thumbnail
  - One-click load
  - Fully editable (not locked)

- [ ] **Built-in Templates**
  - Dreamy Profile (glass cards, pink gradients)
  - Ocean Theme (blues, bubbles, waves)
  - Y2K (chrome, glossy, stars)
  - Gothic (ornate, serif, dark)
  - Cyberpunk (neon, grid, glitch)
  - Scrapbook (tape, photos, stickers)
  - Anime Character Page (stats, gallery, relations)
  - Fake OS (windows, taskbar)
  - Music Player (album art, controls)
  - Minimal (sans-serif, whitespace)

- [ ] **Theme System**
  - Global color palette
  - Typography defaults
  - Shadow/glow defaults
  - Apply theme to new projects
  - Switch theme mid-project

- [ ] **Theme Variables**
  ```css
  --background
  --foreground
  --primary
  --secondary
  --accent
  --muted
  --border
  --shadow
  --radius
  --font-heading
  --font-body
  ```

- [ ] **Custom Theme Creator**
  - Edit theme variables
  - Live preview
  - Save custom themes
  - Export theme as JSON

- [ ] **Effect Presets** (Expanded)
  - Glassmorphism, frosted glass, neon glow, soft glow
  - Y2K chrome, holographic, scanlines
  - VHS, glitch, chromatic aberration
  - Pixelation, film grain, bloom
  - 20+ total presets
  - Each one-click applicable
  - All editable afterward

### Deliverables

- 20+ templates
- 8+ themes
- 20+ effect presets
- Theme customizer UI

### Technical Notes

- Store templates in `/templates` directory as JSON
- Each template is a full project export
- Theme system via CSS custom properties
- Use `createElement()` with theme-aware defaults

---

## PHASE 7: Asset Management & Media Library

**Duration:** 1–2 weeks  
**Focus:** Build a comprehensive asset management system.

### Goals

- [ ] **Asset Upload**
  - Drag-and-drop image upload
  - Video upload
  - Audio upload
  - SVG upload
  - GIF support
  - WebP, PNG, JPG formats

- [ ] **Asset Organization**
  - Create folders/categories
  - Tag assets
  - Rename, delete, duplicate
  - Search by name/tag
  - Favorite/star assets

- [ ] **Asset Preview**
  - Thumbnail grid
  - Large preview modal
  - File size, dimensions
  - Copy file URL

- [ ] **Asset Insertion**
  - Drag asset onto canvas
  - Right-click "Insert" option
  - Auto-size image elements
  - Batch insert

- [ ] **IndexedDB Storage**
  - Store uploaded assets in browser
  - Fallback to base64 for small assets
  - Persist across sessions
  - Clear storage option

- [ ] **Asset Export**
  - Download original files
  - Export all project assets as ZIP
  - Replace URLs in exported HTML with local files (optional)

### Deliverables

- Full asset manager
- Drag-and-drop asset insertion
- IndexedDB persistence
- Asset export system

### Technical Notes

- Use File API for uploads
- IndexedDB for large asset storage
- Base64 fallback for localStorage-based projects
- Asset reference format: `asset://{assetId}` or direct URL

---

## PHASE 8: Responsive Design & Code Integration

**Duration:** 2–3 weeks  
**Focus:** Support responsive design and deep HTML/CSS/JavaScript editing.

### Goals

- [ ] **Responsive Breakpoints**
  - Define breakpoints (Mobile, Tablet, Desktop)
  - Custom breakpoint editor
  - Per-breakpoint styling (font size, spacing, visibility)
  - Preview at different sizes
  - Media query generation

- [ ] **Responsive Inspector**
  - Show current breakpoint
  - Live viewport resize
  - Presets (iPhone, iPad, Desktop)
  - Custom size input

- [ ] **Code Editor Enhancement**
  - Syntax highlighting (HTML, CSS, JS)
  - Line numbers
  - Error detection
  - Auto-indentation
  - Bracket matching
  - Search/replace

- [ ] **HTML Tab**
  - Generate clean, readable HTML
  - Preserve user code sections
  - Export with inline CSS/JS option

- [ ] **CSS Tab**
  - Full CSS output
  - Organized by selector
  - Media queries for responsive
  - Custom user CSS support

- [ ] **JavaScript Tab**
  - User can write custom JavaScript
  - Interaction scripts
  - Animation enhancements
  - Event listeners
  - Sandboxed execution (for security)

- [ ] **Two-Way Sync** (Limited)
  - Visual changes update code (when practical)
  - Code changes update canvas (live preview)
  - User code preserved and editable

### Deliverables

- Responsive design support
- Advanced code editor
- JavaScript integration
- Media query generation

### Technical Notes

- Use Monaco Editor or CodeMirror for code editor
- Store user code separately in `element.customCode`
- Generate responsive CSS at export time
- Sandbox user JavaScript in iframe with restrictions

---

## PHASE 9: Pinterest Integration & Inspiration Tools

**Duration:** 2 weeks  
**Focus:** Connect to Pinterest for visual inspiration (official API only).

### Goals

- [ ] **Pinterest OAuth**
  - Secure OAuth login flow
  - No password storage
  - Backend endpoint for token exchange
  - Token refresh handling

- [ ] **Pinterest Panel**
  - Connected user display
  - Search Pinterest (via official API)
  - Browse saved boards
  - Browse pins from specific board
  - Save/bookmark pins to inspiration board

- [ ] **Inspiration Board**
  - Internal moodboard
  - Drag and arrange images
  - Add notes/colors/text
  - Organize into folders
  - Right-click "Use as Reference"
  - Color sampling from images

- [ ] **Reference Library**
  - Collect color palettes
  - Collect typography samples
  - Save SVG snippets
  - Organize by project/mood

- [ ] **Pinterest API Compliance**
  - Use official endpoints only
  - No scraping
  - Respect rate limits
  - Handle API errors gracefully
  - Provide "Open on Pinterest" fallback

- [ ] **Privacy & Security**
  - Store OAuth token server-side
  - Never expose in client JavaScript
  - CORS proxy for API calls (optional)
  - Clear token on logout

### Deliverables

- Working Pinterest OAuth login
- Pinterest search and browse
- Internal inspiration board
- Color extraction tool

### Technical Notes

- Create backend API route: `/api/auth/pinterest`
- Pinterest API endpoint: `https://api.pinterest.com/v1/`
- Store tokens in secure HTTP-only cookies
- Implement token refresh logic
- Use CORS-safe requests

---

## PHASE 10: AI Assistant & Generative Design

**Duration:** 3–4 weeks  
**Focus:** Integrate AI for intelligent design suggestions and generation.

### Goals

- [ ] **AI Chat Interface**
  - Conversation history
  - Project context awareness
  - Design-specific prompts
  - Typing indicator
  - Error handling

- [ ] **AI Capabilities**
  - **Suggest Changes**: "Make this card more glassy"
  - **Generate CSS**: "Create a Y2K effect"
  - **Generate SVG**: "Draw a starfield animation"
  - **Create Elements**: "Add a glass button"
  - **Fix Issues**: "This text is hard to read"
  - **Explain Code**: "What does this CSS do?"
  - **Color Palettes**: "Suggest a dreamy color palette"
  - **Typography**: "Recommend a font pairing"
  - **Layout Ideas**: "How should I arrange these?"

- [ ] **Project Context**
  - AI understands current project
  - Can reference selected element
  - Aware of canvas size, theme, elements
  - Suggests contextually relevant changes

- [ ] **Design Actions**
  - **Preview**: Show AI suggestion before applying
  - **Apply**: Accept and apply suggestion
  - **Cancel**: Reject suggestion
  - **Refine**: Iterate on suggestion
  - **Undo**: Revert if unsatisfied

- [ ] **AI Code Generation**
  - Generate valid HTML/CSS/SVG
  - Preserve existing code structure
  - Match project style/theme
  - No hallucinated APIs or libraries

- [ ] **API Abstraction**
  - Support multiple AI providers (OpenAI, Anthropic, etc.)
  - Configurable backend endpoint
  - Secure API key handling
  - Rate limiting, quota management
  - Fallback to offline suggestions (optional)

- [ ] **Generative Elements**
  - Particle fields (configurable)
  - SVG patterns
  - Animated gradients
  - Procedural backgrounds
  - Noise/texture generators

- [ ] **Prompt Templates**
  - Quick prompts for common tasks
  - "Make it glassmorphic", "Add glow", "Create animation"
  - Smart prompt suggestions based on context

### Deliverables

- Functional AI chat drawer
- Multiple design action types
- Context-aware suggestions
- Secure API integration
- 10+ smart prompt templates
- Procedural generation tools

### Technical Notes

- Create `AIService` with provider abstraction
- Backend route: `/api/ai/chat` (with auth)
- Store conversations in IndexedDB (optional)
- Use streaming responses for live updates
- Parse AI output carefully (CSS, SVG, etc.)
- Sanitize generated code
- Rate limit to 10 requests/minute per user

---

## Implementation Order & Dependencies

```
PHASE 1 (Foundation)
    ↓
PHASE 2 (CSS Lab) — can run parallel with Phase 3
    ↓
PHASE 3 (Refactoring) — stabilizes codebase
    ↓
PHASE 4 (SVG) — independent feature
    ↓
PHASE 5 (Animation) — builds on Phase 2 styles
    ↓
PHASE 6 (Templates & Themes) — uses Phases 2, 4, 5
    ↓
PHASE 7 (Assets) — independent, improves all phases
    ↓
PHASE 8 (Responsive & Code) — enhances export from all phases
    ↓
PHASE 9 (Pinterest) — optional, independent
    ↓
PHASE 10 (AI) — ties everything together
```

---

## Priority & MVP Definition

**Minimum Viable Product (MVP):** Phases 1–3 + Phase 2 styling  
**Full Studio:** All 10 phases

---

## Estimated Timeline

| Phase | Duration | Cumulative |
|-------|----------|-----------|
| 1 | 1–2 weeks | 1–2 weeks |
| 2 | 2–3 weeks | 3–5 weeks |
| 3 | 1–2 weeks | 4–7 weeks |
| 4 | 2–3 weeks | 6–10 weeks |
| 5 | 2–3 weeks | 8–13 weeks |
| 6 | 1–2 weeks | 9–15 weeks |
| 7 | 1–2 weeks | 10–17 weeks |
| 8 | 2–3 weeks | 12–20 weeks |
| 9 | 2 weeks | 14–22 weeks |
| 10 | 3–4 weeks | 17–26 weeks |

**Full build: 4–6 months** (with one developer, full-time)

---

## Quality Gates

Each phase must meet:

- ✓ All listed goals implemented
- ✓ No regressions from previous phases
- ✓ UI tested at common breakpoints
- ✓ Code reviewed for modularity
- ✓ Performance acceptable (< 100ms interaction latency)
- ✓ Error handling for edge cases
- ✓ User documentation started

---

## Notes for Future Development

1. **Testing**: Begin unit tests in Phase 3, expand through each phase
2. **Performance**: Profile and optimize in Phase 3 and Phase 8
3. **Accessibility**: Audit WCAG 2.1 compliance in each phase
4. **Documentation**: Maintain updated README and help guides
5. **Community**: Collect feedback after Phase 1 MVP release
6. **Security**: Audit in Phase 3, 8 (code execution), 9 (OAuth), 10 (API)
7. **Browser Support**: Test Chrome, Firefox, Safari, Edge after each phase
8. **Mobile**: Optimize UI for touch in Phase 3+

---

This roadmap is a living document. Adjust timelines and priorities based on feedback and resource availability.
