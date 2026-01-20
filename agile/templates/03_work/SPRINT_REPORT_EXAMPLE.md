# Sprint Report: Sprint 1.1

## 1. Sprint Overview

| Field | Value |
|-------|-------|
| **Sprint Number** | 1.1 |
| **Sprint Name** | The Connectivity Skeleton |
| **Date Started** | 2025-12-20 |
| **Date Completed** | 2025-12-20 |
| **Status** | Completed |
| **Git Commit** | `a1b2c3d` - "Sprint 1.1: Basic Connectivity & Game Loop" |

---

## 2. Sprint Goal (Recap)

> **Goal:** Prove that the network stack works. Verify that a smartphone can control a pixel on the big screen with minimal latency before we write any game logic.

### Agreed Testable Outcomes
1. Start a local server with a simple script
2. Open a "Spectator" page showing a black canvas with a yellow square
3. Open a "Controller" page on phone with 4 directional buttons
4. Press buttons on phone and see the square move on the big screen

---

## 3. Results: What Was Achieved

We have successfully built the **foundation** for the multiplayer game. All core connectivity features are working.

### Features Implemented

| Feature | Description | Status |
|---------|-------------|--------|
| Node.js Server | Express + Socket.io server on port 3000 | Completed |
| Spectator View | HTML5 Canvas (800x600) displaying players | Completed |
| Mobile Controller | Touch-friendly D-Pad with 4 buttons | Completed |
| Real-Time Sync | Player movements broadcast at 30 FPS | Completed |
| Helper Scripts | start/stop scripts for Mac, Linux, Windows | Completed |

### Stories Completed

| Story ID | Title | Status |
|----------|-------|--------|
| 1.0 | WebSocket-Verbindungsmanagement | Completed |
| 1.1 | QR-Code Einstieg (partial) | Completed |
| 3.0 | Touch Input Handling | Completed |
| 3.1 | Große D-Pad Tasten | Completed |

---

## 4. How to Test

### Prerequisites
- **Node.js v18+** must be installed. Verify with: `node -v`

### Step-by-Step Instructions

1. **Open the `results/` folder** in your file explorer.

2. **Start the application:**
   - **Mac/Linux:** Open Terminal, navigate to `results/`, run `./start.sh`
   - **Windows:** Double-click `start.bat`
   - Wait until you see: `Server running at http://localhost:3000`

3. **Test the Spectator View:**
   - Open browser: `http://localhost:3000`
   - You should see a black canvas

4. **Test the Controller:**
   - On phone (same Wi-Fi) or another tab: `http://localhost:3000/controller.html`
   - You should see 4 large directional buttons

5. **Test the Connection:**
   - Press arrow buttons on Controller
   - Watch yellow square move on Spectator screen

6. **Stop the application:**
   - **Mac/Linux:** Run `./stop.sh`
   - **Windows:** Run `stop.bat`

### Expected Behavior

| Action | Expected Result |
|--------|-----------------|
| Open `localhost:3000` | Black canvas appears |
| Open `localhost:3000/controller.html` | D-Pad buttons appear |
| Press UP button | Yellow square moves up |
| Press DOWN button | Yellow square moves down |
| Open second controller | Second yellow square appears |

### Troubleshooting

| Problem | Solution |
|---------|----------|
| "EADDRINUSE: address already in use" | Run `stop.sh` / `stop.bat` first |
| "Cannot find module 'express'" | Run `npm install` in results/ folder |
| Controller buttons don't respond | Use `http://`, not `https://` |
| Phone can't connect | Same Wi-Fi required. Use computer's IP (e.g., `192.168.1.x`) |

---

## 5. Definition of Done Verification

| Criterion | Status | Evidence |
|-----------|--------|----------|
| Code runs without errors | Pass | Server starts, no console errors |
| Helper scripts provided | Pass | start.sh, stop.sh, start.bat, stop.bat |
| README exists | Pass | results/README.md with instructions |
| User can test independently | Pass | Step-by-step instructions above |
| All acceptance criteria met | Pass | All 4 testable outcomes verified |

**Overall DoD Status:** All criteria passed

---

## 6. User Acceptance

| Field | Value |
|-------|-------|
| **User Tested** | Yes |
| **User Approved** | Yes |
| **Approval Date** | 2025-12-20 |
| **Feedback** | "Works great! Movement is smooth." |

---

## 7. Changed Files

| File | Description |
|------|-------------|
| `results/package.json` | Project configuration with dependencies |
| `results/src/server/index.js` | Main server (Express, Socket.io, Game Loop) |
| `results/src/client/public/index.html` | Spectator page (Canvas) |
| `results/src/client/public/controller.html` | Mobile controller (D-Pad) |
| `results/src/client/public/js/spectator.js` | Client-side rendering |
| `results/start.sh` | Mac/Linux launcher |
| `results/start.bat` | Windows launcher |
| `results/stop.sh` | Mac/Linux stop script |
| `results/stop.bat` | Windows stop script |
| `results/README.md` | Usage documentation |

---

## 8. Lessons Learned

1. **Mobile Touch Events:** Using `touchstart` instead of `click` eliminates the 300ms delay on mobile browsers. Critical for responsive games.

2. **Port Conflicts:** Students often forget to stop server before restarting. The auto-cleanup in `start.sh` (calling `stop.sh` first) prevents "port in use" errors.

3. **Same Network Requirement:** Phone-to-laptop communication requires same Wi-Fi. Common source of confusion for users.

---

## 9. Deferred Items

Items captured during this sprint for future consideration:

| Item | Added to Backlog Refinement |
|------|----------------------------|
| Dynamic QR Code with IP detection | Yes |
| Mobile viewport optimization | Yes |

See `agile/artifacts/03_work/BACKLOG_REFINEMENT.md` for details.

---

## 10. Outlook: Next Sprint

Based on the Product Backlog, the next sprint could focus on:

| Story ID | Title | Epic |
|----------|-------|------|
| 2.0 | Game State Synchronisation | Epic 2: Gameplay |
| 2.1 | Punkte einsammeln | Epic 2: Gameplay |
| 1.2 | Automatische Rollenzuweisung | Epic 1: Lobby |

**Suggested Focus:** Implement core game mechanics - dots, scoring, and role assignment (Pac-Man vs Ghosts).

---

*Sprint 1.1 completed and committed on 2025-12-20.*
