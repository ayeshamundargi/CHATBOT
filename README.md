# NEXA — Fluid Intelligence AI Workspace

**NEXA** is a self-contained, zero-build AI chatbot web application that combines a full-viewport WebGL Navier-Stokes fluid-ink canvas with a morphing glassmorphic conversational workspace.

## Features

- **WebGL Fluid-Ink Canvas:** Interactive Navier-Stokes fluid simulation (`SIM_RESOLUTION: 200`, `DYE_RESOLUTION: 512`, vorticity confinement, specular shading, orbiting auto-cursor, and passive pointer tracking) that reacts with directional ink bursts on user prompts, AI responses, and mode switches.
- **Hero-to-Chat Morphing UI:** Word-by-word entrance typography (`Onest`) that smoothly transitions into a centered glassmorphic chat thread (`max-width: 52rem`) on first message, paired with Lenis smooth scrolling.
- **Four Focus Modes:**
  - **Deep Work** (cyan → blue) — structured, first-principles analysis
  - **Code** (emerald → teal) — idiomatic code blocks, edge cases, and copy buttons
  - **Creative** (violet → magenta) — expressive narrative framing and brainstorming
  - **Concise** (electric indigo → ice) — tight, high-signal takeaways
- **Flexible AI Connections:**
  - **Gemini API** (`gemini-3.8-flash` default, plus `gemini-3.6-flash`, `gemini-3.5-flash-lite`, or any custom model ID) with streaming SSE and automatic retry/fallback handling for transient capacity spikes
  - **Custom Backend Endpoint** (OpenAI-compatible SSE or JSON)
  - **Built-in Demo Mode** when no API key is configured, so the app works immediately out of the box
- **Login Page & Guest Access:** Full-bleed glassmorphic Sign In / Create Account screen over the live WebGL fluid canvas with client-side SHA-256 credential storage, accessible validation, and one-click Guest mode.
- **Solving Goals Workspace:** Create goals tied to a Focus Mode, manage step checklists, mark goals solved, or click **Solve with NEXA** to generate an execution plan directly in chat.
- **Live Analytics Dashboard:** Real-time KPI cards, Focus Mode distribution bars, and a 7-day SVG activity chart computed from local conversations and solved goals.
- **Local Persistence & Controls:** Conversations are saved locally in `localStorage` via the slide-over **Conversations** drawer (open, inline rename, delete, clear all), with full keyboard support (`Enter` to send, `Shift+Enter` for newline, `Esc` to dismiss modals/drawers) and a background ink pause/play toggle.

## Project Structure

- `index.html` — Complete self-contained HTML, CSS, WebGL fluid engine, Markdown/table renderer, and client logic
- `render.yaml` — Render Blueprint configuration for zero-build static site deployment

## Run Locally

Open `index.html` directly in a modern browser, or serve the folder with any static server:

```bash
python -m http.server 8080
```

Then visit `http://localhost:8080`.

## Deploy to Render

1. Push this repository to GitHub.
2. In the Render dashboard, select **New → Blueprint** (or **New → Static Site** with Publish Directory `.` and a blank Build Command) and connect this repository.
3. Render uses `render.yaml` to publish the static site automatically.

