# Sprint Backlog: Sprint 1.1

## 1. Sprint Information

| Field | Value |
|-------|-------|
| **Sprint Number** | 1.1 |
| **Sprint Name** | The Connectivity Skeleton |
| **Date Started** | 2025-12-20 |
| **Status** | Completed |

### Source Stories (from Product Backlog)

| Story ID | Title | Epic |
|----------|-------|------|
| 1.0 | WebSocket-Verbindungsmanagement | Epic 1: Lobby & Einstieg |
| 1.1 | QR-Code Einstieg (partial) | Epic 1: Lobby & Einstieg |
| 3.0 | Touch Input Handling | Epic 3: Mobile Controller |
| 3.1 | Große D-Pad Tasten | Epic 3: Mobile Controller |

---

## 2. Sprint Goal

### What are we building?
We are proving that the **network stack works**. Before writing any game logic, we need to verify that a smartphone can send commands to a server, and that server can update a shared display in real-time. This is the foundation for everything else.

### Testable Outcomes (User Agreement)
At the end of this sprint, you will be able to:
1. Start a local server with a simple script
2. Open a "Spectator" page showing a black canvas with a yellow square
3. Open a "Controller" page on your phone with 4 directional buttons
4. Press buttons on your phone and see the square move on the big screen

### Sprint Acceptance Criteria
- [x] Server starts without errors using `start.sh` or `start.bat`
- [x] Spectator page displays at `http://localhost:3000`
- [x] Controller page works on mobile browser
- [x] Button presses result in visible movement (latency < 100ms)

---

## 3. Tasks

### Task 1: Project Initialization & Scaffold

| Field | Value |
|-------|-------|
| **Source Story** | 1.0 (WebSocket-Verbindungsmanagement) |
| **Status** | [x] Done |
| **Verified** | [x] Yes |

**Description:**
Set up the Node.js project structure with Express and Socket.io.

**Technical Approach:**
- Run `npm init` to create `package.json`
- Install dependencies: `express`, `socket.io`, `qrcode`
- Create folder structure: `src/server/`, `src/client/public/`

**Acceptance Criteria:**
- [x] `package.json` exists with correct dependencies
- [x] `npm install` runs without errors

**Verification Method:**
Run `npm install` and check for errors. Verify `node_modules/` is created.

---

### Task 2: WebSocket Server (Hello World)

| Field | Value |
|-------|-------|
| **Source Story** | 1.0 (WebSocket-Verbindungsmanagement) |
| **Status** | [x] Done |
| **Verified** | [x] Yes |

**Description:**
Verify that a client can connect to the server via WebSocket.

**Technical Approach:**
- Implement `io.on('connection')` on the server
- Log "User connected" when a client joins
- Send a welcome message back to the client

**Acceptance Criteria:**
- [x] Opening `http://localhost:3000` logs a message in the server console
- [x] The browser console shows the welcome message

**Verification Method:**
Start server, open browser to localhost:3000, check server console for "User connected".

---

### Task 3: Mobile D-Pad Controller

| Field | Value |
|-------|-------|
| **Source Story** | 3.0, 3.1 (Touch Input, D-Pad Tasten) |
| **Status** | [x] Done |
| **Verified** | [x] Yes |

**Description:**
Create a mobile-friendly HTML page with 4 directional buttons.

**Technical Approach:**
- Create `controller.html` with large touch-friendly buttons
- Use `touchstart` events (not `click`) to avoid 300ms mobile delay
- Emit socket events: `socket.emit('input', 'UP')`

**Acceptance Criteria:**
- [x] Controller page renders correctly on smartphone
- [x] Touching a button emits the correct direction to server

**Verification Method:**
Open localhost:3000/controller.html on phone (same WiFi). Press buttons, verify server receives input.

---

### Task 4: Canvas Rendering (Spectator)

| Field | Value |
|-------|-------|
| **Source Story** | 1.1 (QR-Code Einstieg) - partial |
| **Status** | [x] Done |
| **Verified** | [x] Yes |

**Description:**
Display connected players as colored squares on an HTML5 Canvas.

**Technical Approach:**
- Create `index.html` with a `<canvas>` element (800x600)
- Use `requestAnimationFrame` for smooth rendering
- Listen for `stateUpdate` events and draw player positions

**Acceptance Criteria:**
- [x] Canvas displays black background
- [x] Each connected player appears as yellow square
- [x] Movement is smooth and responsive

**Verification Method:**
Open spectator in one browser, controller in another. Press buttons, verify square moves smoothly.

---

### Task 5: Helper Scripts (Mandatory)

| Field | Value |
|-------|-------|
| **Source Story** | Infrastructure |
| **Status** | [x] Done |
| **Verified** | [x] Yes |

**Description:**
Create user-friendly scripts to start and stop the server.

**Deliverables:**
- [x] `results/start.sh` (Mac/Linux)
- [x] `results/start.bat` (Windows)
- [x] `results/stop.sh` (Mac/Linux)
- [x] `results/stop.bat` (Windows)
- [x] `results/README.md` (Usage instructions)

**Acceptance Criteria:**
- [x] `start.sh`/`.bat` launches the server
- [x] `start.sh`/`.bat` calls stop script first (prevents port conflicts)
- [x] `stop.sh`/`.bat` cleanly terminates the server

**Verification Method:**
Run `./start.sh`, verify server starts. Run `./stop.sh`, verify process terminates. Run `./start.sh` again, verify no "EADDRINUSE" error.

---

## 4. Progress Summary

| Task | Status | Verified |
|------|--------|----------|
| Task 1: Project Scaffold | [x] Done | [x] |
| Task 2: WebSocket Server | [x] Done | [x] |
| Task 3: Mobile D-Pad | [x] Done | [x] |
| Task 4: Canvas Spectator | [x] Done | [x] |
| Task 5: Helper Scripts | [x] Done | [x] |

**Overall Progress:** 5 / 5 tasks complete

---

## 5. Notes & Decisions

| Date | Note |
|------|------|
| 2025-12-20 | **Vanilla JS:** Decided to use plain JavaScript without frameworks (React, Vue) to avoid dependency complexity. Students can understand the code directly. |
| 2025-12-20 | **Fixed Canvas Size:** Canvas is hardcoded to 800x600 pixels. Responsive design is out of scope for this sprint. |
| 2025-12-20 | **Port 3000:** Using default port 3000. If users have conflicts, they can change it in `index.js`. |
| 2025-12-20 | **QR Code Deferred:** Full QR code feature (Story 1.1) is partially deferred. We need stable IP detection first. For now, users manually type the URL. |

---

## 6. Deferred Items

Items that came up during this sprint but were moved to Backlog Refinement:

| Item | Reason Deferred | Added to Refinement |
|------|-----------------|---------------------|
| Dynamic QR Code with IP detection | Need cross-platform IP detection | [x] Yes |
| Mobile viewport optimization | Nice-to-have, not blocking | [x] Yes |
