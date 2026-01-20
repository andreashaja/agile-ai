# Project Vision: Pac-Party

**Date:** Sat Jan 17 2026
**Status:** Inception Complete

---

## 1. Elevator Pitch

**For** prospective students at university trade fairs,
**who** are looking for an entertaining first contact with the Computer Science department,
**Pac-Party is** a browser-based multiplayer game,
**that** allows up to 5 visitors to compete against each other simultaneously - no app download required, just scan a QR code and start playing.

---

## 2. Business Goals

- **Crowd Magnet:** Attract trade fair visitors to the booth through an interactive game
- **Low Barrier to Entry:** Instant game start without app installation or account creation
- **High Rotation:** Short rounds (2-3 min) allow many visitors to participate
- **Brand Building:** Positive first impression of the Computer Science department

---

## 3. Target Audience

| Role | Description | Need |
|------|-------------|------|
| **Player** | Trade fair visitors (primarily prospective students) | Have fun, join quickly |
| **Spectator** | Passersby attracted by the screen | Be entertained, understand what's happening |
| **Booth Staff** | Department employees | Game runs autonomously, no explanation effort |

---

## 4. Scope

### In Scope (What we build)

| Area | Details |
|------|---------|
| **Large Screen** | Game field, timer, score, QR code to join, department logo, highscore list |
| **Phone Controller** | Web app with D-Pad controls, role indicator (color), game status |
| **Game Mechanics** | Classic Pac-Man: eat dots, power pellets, chase/flee ghosts |
| **Lobby System** | QR code entry, 5 player slots, waiting queue, auto-fill on disconnect |
| **Round Logic** | 2-3 minute timer, ends on timeout or Pac-Man caught, then new lobby |
| **Feedback** | Sound effects (screen), vibration (controller) |
| **Network** | Local network (own router + server laptop) |

### Out of Scope (What we deliberately do NOT build)

| Exclusion | Reason |
|-----------|--------|
| Login / Accounts | Barrier to quick entry |
| Chat Function | Unnecessary - players stand next to each other |
| Persistent Data | Only daily highscore, nothing stored permanently |
| Native Mobile App | Web-based is sufficient, no App Store needed |
| Multiple Levels/Maps | One classic maze is enough for trade fair context |
| Tournament Mode | Overkill for spontaneous trade fair visitors |

---

## 5. Constraints & Risks

### Constraints

- **Network:** Trade fair WiFi is unreliable → own local network required
- **Hardware:** Requires large screen/projector + laptop as server + router
- **Self-Explanatory:** Must work without instructions (no permanent booth staff)

### Risks

| Risk | Impact | Mitigation |
|------|--------|------------|
| WiFi Problems | Players cannot join | Own router, local network |
| Overcrowding | Long wait times, frustration | Waiting queue with clear position |
| Browser Compatibility | Controller doesn't work | Test on common mobile browsers |
| Disconnect During Game | Game blocks | Automatic fill-in from waiting queue |

---

## 6. Roadmap (Epics)

| # | Epic | Business Value |
|---|------|----------------|
| **1** | **Lobby & Entry** | Minimizes time from "walking by" to "playing" |
| **2** | **Gameplay (Core)** | The heart of it - no working Pac-Man, no game |
| **3** | **Mobile Controller** | Enables intuitive control, eyes stay on large screen |
| **4** | **Display (Large Screen)** | The "wow factor" - attracts spectators, shows everything important |

---

## 7. Success Metrics

| Metric | Target |
|--------|--------|
| Time to Game Start | < 30 seconds (QR scan to lobby) |
| Average Round Duration | 2-3 minutes |
| Player Rotation per Hour | 20+ different players |
| Comprehensibility | Players need no explanation from staff |
