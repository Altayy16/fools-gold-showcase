# Fools Gold - UI/UX Design System

## 🛡️ 1. Core Visual Philosophy
The *Fools Gold* interface is built on a "Dark Tavern" aesthetic. It balances the nostalgia of pixel-art environments with high-fidelity 3D assets and crisp, modern UI overlays. The design system is heavily optimized for mobile (React Native/Capacitor safe areas) ensuring high contrast and immediate readability during fast-paced, real-time multiplayer sessions.

## 🎨 2. Color Architecture
The application utilizes a strict, highly semantic color palette, mapped to Tailwind CSS utility conventions for scalable frontend development.

### Backgrounds & Surfaces (The Tavern)
* **Base Dark:** `bg-stone-950` / `#0C0A09` (Used for app backgrounds and deep space).
* **Surface Panels:** `bg-stone-900/90` with heavy backdrop blur (Used for modals, waiting rooms, and inventory panels). 
* **Borders:** Subtle golden strokes (`border-amber-700/50`) to separate panels without visual clutter.

### Interactive & Semantic Colors
* **Primary Action (Gold/Fire):** A vibrant gradient `from-orange-500 to-amber-600`. Used strictly for advancing the game loop (e.g., "START GAME", "SAVE CHANGES", "Play Again").
* **Positive Action / Success:** `bg-emerald-500` (Used for the "BID" action and success checkmarks).
* **Negative Action / Danger:** `bg-red-600` (Used for "PASS", "Close Room", and "CALL BLUFF" mechanics).
* **Currency Indicators:** Bright Yellow/Gold for standard currency, Cyan for premium Diamonds.

## 🖋️ 3. Typography System
A dual-font system is employed to separate thematic flavor from critical game data.
* **Display Font (Thematic Serif):** A classic, high-contrast serif (used for "FOOL'S GOLD", "GAME OVER!", and Item Titles). It provides the medieval fantasy flavor. Always rendered in crisp white or pale gold.
* **Data Font (System Sans-Serif):** A highly legible, monospaced-friendly sans-serif (used for user IDs, timers, and currency balances). Crucial for readability on small mobile screens when numbers are updating in real-time.

## 📐 4. Component Library Rules

### Buttons
* **Shape:** Fully rounded pills (`rounded-full`) for navigation tabs, and soft-rectangles (`rounded-xl` or `rounded-2xl`) for major call-to-action buttons.
* **State Feedback:** All interactive elements feature immediate visual feedback (scale down on press, opacity changes) to mask network latency during WebSocket round-trips.

### Game Cards (The Core Interactive Element)
* **Visual Hierarchy:** 1. High-fidelity item artwork in the center.
  2. Thematic Serif title directly below.
  3. Bold, Sans-Serif exact value indicator (`Value: 80$`) in semantic colors (Green for profit, Red for negative curse values like `-50$`).

## 📱 5. UX & State Management Principles

### Precision Economy (The "No Truncation" Rule)
To maintain absolute player trust in the economy, currency values are **never truncated**. As seen in the main lobby, a balance of `1,029,505` is displayed in its entirety rather than lazy shorthand like `1M` or `1,029K`. The frontend UI is designed to scale dynamically to accommodate large `BIGINT` integer strings without breaking the layout.

### Real-Time Turn Prompts
Because the game state is dictated by an authoritative backend via WebSockets, the UI employs highly visible, floating active-state prompts (e.g., the glowing orange "Altay: THINKING..." progress bar) so players instantly know whose turn it is, reducing friction and AFK timeouts.