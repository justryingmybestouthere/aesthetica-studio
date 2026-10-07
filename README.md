* {
  box-sizing: border-box;
}

:root {
  color-scheme: dark;
  --bg: #090d1a;
  --panel: #121a2a;
  --panel-alt: #171f31;
  --panel-soft: rgba(255, 255, 255, 0.04);
  --border: rgba(255, 255, 255, 0.1);
  --text: #edf3ff;
  --muted: #a6b1c8;
  --accent: #f5b2d3;
  --accent-2: #8cc8ff;
  --shadow: rgba(15, 19, 33, 0.75);
  --radius: 18px;
  font-family: 'Inter', sans-serif;
}

html, body {
  margin: 0;
  min-height: 100%;
  background:
    radial-gradient(circle at top left, rgba(156, 164, 255, 0.18), transparent 25%),
    radial-gradient(circle at bottom right, rgba(250, 167, 214, 0.18), transparent 32%),
    var(--bg);
  color: var(--text);
}

body {
  min-height: 100vh;
}

button, input, select, textarea {
  font: inherit;
}

button {
  cursor: pointer;
}

#app {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
  background: rgba(7, 11, 19, 0.78);
  backdrop-filter: blur(10px);
}

#app.theme-dark {
  --bg: #090d1a;
  --panel: #111827;
  --panel-alt: #121d2f;
  --border: rgba(255,255,255,0.12);
  --text: #edf3ff;
  --muted: #a6b1c8;
  --accent: #f5b2d3;
  --accent-2: #8cc8ff;
}

#app.theme-dream {
  --bg: #f6eef4;
  --panel: #fffdfd;
  --panel-alt: #f7ebf5;
  --border: rgba(132, 101, 118, 0.18);
  --text: #2f2030;
  --muted: #6d586a;
  --accent: #ff9cc3;
  --accent-2: #9ec7ff;
}

.topbar {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 16px 22px;
  border-bottom: 1px solid var(--border);
  background: rgba(17, 24, 39, 0.7);
}

.brand-wrap {
  display: flex;
  align-items: center;
  gap: 12px;
  letter-spacing: 0.14em;
}

.brand-mark {
  display: grid;
  place-items: center;
  width: 28px;
  height: 28px;
  border-radius: 10px;
  background: linear-gradient(135deg, rgba(255, 181, 219, 0.9), rgba(141, 199, 255, 0.9));
  color: #111827;
  font-weight: 900;
}

.brand-text {
  font-size: 0.88rem;
  font-weight: 800;
  letter-spacing: 0.2em;
}

.topbar-actions {
  display: flex;
  align-items: center;
  gap: 10px;
}

.primary-btn,
.ghost-btn,
.tool-btn,
.icon-btn,
.library-item,
.tab-btn {
  border: 1px solid var(--border);
  border-radius: 12px;
  background: rgba(255,255,255,0.03);
  color: var(--text);
  transition: transform 160ms ease, border-color 160ms ease, box-shadow 160ms ease;
}

.primary-btn,
.ghost-btn {
  padding: 10px 14px;
}

.primary-btn {
  background: linear-gradient(135deg, rgba(245,178,211,1), rgba(140,200,255,1));
  color: #0b0f19;
  font-weight: 800;
}

.workspace {
  display: grid;
  grid-template-columns: 290px minmax(0, 1fr) 300px;
  flex: 1 1 auto;
  min-height: 0;
}

.panel {
  background: rgba(16, 20, 31, 0.68);
  border-right: 1px solid var(--border);
  padding: 14px 12px;
  min-height: 0;
}

.right-panel {
  border-left: 1px solid var(--border);
  border-right: none;
}

.panel-group {
  display: flex;
  flex-direction: column;
  gap: 12px;
  margin-bottom: 18px;
}

.group-header {
  font-size: 0.7rem;
  color: var(--muted);
  letter-spacing: 0.18em;
  font-weight: 700;
  padding: 6px 8px;
}

.library-grid {
  display: grid;
  grid-template-columns: repeat(2, minmax(0, 1fr));
  gap: 10px;
}

.library-item {
  padding: 14px 12px;
  min-height: 72px;
  text-align: left;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
  gap: 8px;
  background: linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));
}

.center-panel {
  display: flex;
  flex-direction: column;
  min-height: 0;
  padding: 18px 16px 0;
}

.canvas-toolbar {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 12px;
  padding: 12px 8px 14px;
}

.tool-group {
  display: flex;
  align-items: center;
  gap: 8px;
  flex-wrap: wrap;
}

.tool-btn {
  padding: 8px 12px;
}

.right-tools {
  font-size: 0.8rem;
  color: var(--muted);
}

.right-tools label {
  display: flex;
  align-items: center;
  gap: 10px;
}

select {
  background: rgba(255,255,255,0.05);
  border: 1px solid var(--border);
  color: var(--text);
  border-radius: 10px;
  padding: 8px 12px;
}

.canvas-shell {
  flex: 1;
  display: grid;
  place-items: center;
  padding: 18px;
  border: 1px solid var(--border);
  border-radius: 22px;
  background: linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));
  overflow: auto;
}

#canvas {
  position: relative;
  background:
    linear-gradient(135deg, rgba(255, 187, 219, 0.07), rgba(125, 201, 255, 0.08)),
    #0a111d;
  border-radius: 26px;
  box-shadow: inset 0 0 0 1px rgba(255,255,255,0.06), 0 30px 80px rgba(5, 10, 18, 0.6);
  overflow: hidden;
  transform-origin: top left;
  user-select: none;
}

#canvas::before {
  content: "";
  position: absolute;
  inset: 0;
  background-image:
    linear-gradient(rgba(255,255,255,0.02) 1px, transparent 1px),
    linear-gradient(90deg, rgba(255,255,255,0.02) 1px, transparent 1px);
  background-size: 26px 26px;
  pointer-events: none;
}

.canvas-element {
  position: absolute;
  display: flex;
  align-items: center;
  justify-content: center;
  transform-origin: center;
  user-select: none;
  cursor: grab;
  overflow: hidden;
}

.canvas-element.selected {
  outline: 1px solid rgba(255,255,255,0.5);
}

.selection-box {
  position: absolute;
  border: 1px solid rgba(141, 200, 255, 0.8);
  box-shadow: 0 0 0 1px rgba(141,200,255,0.3), 0 0 28px rgba(141,200,255,0.18);
  pointer-events: none;
}

.resize-handle {
  position: absolute;
  width: 10px;
  height: 10px;
  background: linear-gradient(135deg, #dff3ff, #90d8ff);
  border: 1px solid rgba(21,29,44,0.9);
  border-radius: 50%;
  pointer-events: auto;
}

.handle-nw { left: -6px; top: -6px; cursor: nwse-resize; }
.handle-ne { right: -6px; top: -6px; cursor: nesw-resize; }
.handle-se { right: -6px; bottom: -6px; cursor: nwse-resize; }
.handle-sw { left: -6px; bottom: -6px; cursor: nesw-resize; }

.element-text {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 100%;
  height: 100%;
  text-align: center;
  word-wrap: break-word;
  padding: 8px 12px;
}

.svg-wrap,
.image-art,
.card-inner {
  width: 100%;
  height: 100%;
}

.svg-wrap svg {
  width: 100%;
  height: 100%;
  display: block;
}

.properties-panel {
  display: flex;
  flex-direction: column;
  gap: 10px;
}

.property-row {
  display: grid;
  grid-template-columns: 54px minmax(0, 1fr);
  gap: 8px;
  align-items: center;
  font-size: 0.8rem;
  color: var(--muted);
}

.property-row input {
  width: 100%;
  border: 1px solid var(--border);
  border-radius: 10px;
  background: rgba(255,255,255,0.04);
  color: var(--text);
  padding: 8px 10px;
}

.empty-state {
  color: var(--muted);
  line-height: 1.6;
  font-size: 0.9rem;
}

.layer-list {
  list-style: none;
  padding: 0;
  margin: 0;
  display: flex;
  flex-direction: column;
  gap: 6px;
}

.layer-row {
  display: flex;
  align-items: center;
  gap: 8px;
  padding: 8px 10px;
  border-radius: 10px;
  background: rgba(255,255,255,0.03);
  border: 1px solid transparent;
}

.layer-row.selected {
  border-color: var(--border);
}

.layer-toggle {
  border: none;
  background: transparent;
  color: var(--text);
  width: 20px;
  padding: 0;
}

.layer-label {
  flex: 1;
  text-align: left;
  border: none;
  background: transparent;
  color: var(--text);
}

.statusbar {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 12px;
  padding: 12px 18px;
  background: rgba(17, 24, 39, 0.7);
  border-top: 1px solid var(--border);
  font-size: 0.78rem;
  color: var(--muted);
}

.status-right {
  display: flex;
  gap: 12px;
}

.ai-drawer {
  position: fixed;
  right: 20px;
  bottom: 74px;
  width: min(360px, calc(100vw - 40px));
  background: rgba(10, 13, 21, 0.92);
  border: 1px solid var(--border);
  border-radius: 20px;
  box-shadow: 0 22px 80px rgba(5, 10, 18, 0.7);
  overflow: hidden;
  display: flex;
  flex-direction: column;
  transition: transform 180ms ease;
}

.ai-drawer.closed {
  transform: translateY(calc(100% + 20px));
}

.ai-header,
.code-header {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 10px;
  padding: 14px 16px;
  border-bottom: 1px solid var(--border);
  font-weight: 700;
}

.ai-conversation {
  display: flex;
  flex-direction: column;
  gap: 10px;
  padding: 16px;
  min-height: 220px;
  max-height: 300px;
  overflow: auto;
}

.ai-message {
  max-width: 90%;
  border-radius: 14px;
  padding: 10px 12px;
  line-height: 1.5;
  font-size: 0.9rem;
}

.ai-message.system {
  background: rgba(255,255,255,0.04);
}

.ai-message.user {
  align-self: flex-end;
  background: linear-gradient(135deg, rgba(245,178,211,0.22), rgba(140,200,255,0.18));
}

.ai-message.assistant {
  background: rgba(91, 145, 255, 0.12);
}

.ai-input-row {
  display: grid;
  grid-template-columns: minmax(0, 1fr) auto;
  gap: 10px;
  padding: 0 16px 12px;
}

.ai-input-row input {
  border: 1px solid var(--border);
  border-radius: 12px;
  background: rgba(255,255,255,0.04);
  color: var(--text);
  padding: 10px 12px;
}

.ai-actions {
  display: flex;
  gap: 10px;
  padding: 0 16px 16px;
}

.icon-btn {
  width: 30px;
  height: 30px;
  display: grid;
  place-items: center;
}

.code-panel {
  position: fixed;
  right: 26px;
  bottom: 80px;
  width: min(540px, calc(100vw - 40px));
  background: rgba(11, 15, 24, 0.96);
  border: 1px solid var(--border);
  border-radius: 18px;
  overflow: hidden;
  box-shadow: 0 26px 80px rgba(9, 12, 20, 0.8);
}

.code-panel.hidden {
  display: none;
}

.code-tabs {
  display: flex;
  gap: 8px;
  padding: 8px 12px 0;
}

.tab-btn {
  padding: 7px 12px;
}

.tab-btn.active {
  background: rgba(255,255,255,0.08);
}

#code-editor {
  width: 100%;
  min-height: 250px;
  resize: vertical;
  background: rgba(6, 10, 18, 0.95);
  color: #edf5ff;
  border: none;
  padding: 14px 16px 16px;
  outline: none;
  font-family: 'SFMono-Regular', Consolas, monospace;
  font-size: 0.86rem;
  line-height: 1.6;
}

.toast {
  position: fixed;
  left: 50%;
  bottom: 24px;
  transform: translateX(-50%) translateY(16px);
  opacity: 0;
  padding: 10px 14px;
  border-radius: 999px;
  background: rgba(17, 22, 33, 0.9);
  border: 1px solid var(--border);
  color: var(--text);
  transition: opacity 0.18s ease, transform 0.18s ease;
}

.toast.show {
  opacity: 1;
  transform: translateX(-50%) translateY(0);
}

.preview-mode .panel,
.preview-mode .canvas-toolbar,
.preview-mode .topbar,
.preview-mode .statusbar,
.preview-mode .left-panel,
.preview-mode .right-panel,
.preview-mode .ai-drawer,
.preview-mode .code-panel {
  display: none !important;
}

.preview-mode .workspace {
  grid-template-columns: 1fr;
}

.preview-mode .canvas-shell {
  border: none;
  background: transparent;
  padding: 0;
}

@media (max-width: 980px) {
  .workspace {
    grid-template-columns: 1fr;
  }

  .left-panel,
  .right-panel {
    border: 1px solid var(--border);
    border-radius: 16px;
    margin: 8px 16px;
  }

  .topbar {
    flex-direction: column;
    gap: 12px;
  }
}

@media (prefers-reduced-motion: reduce) {
  *, *::before, *::after {
    animation: none !important;
    transition: none !important;
    scroll-behavior: auto !important;
  }
}

README.md
