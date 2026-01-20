# Project Vision v2: Pac-Party

**Date:** Sun Jan 18 2026
**Status:** Architecture Complete
**Version:** 2.0 (Enhanced with Technical Architecture)

---

## 1. Elevator Pitch

**For** prospective students at university fairs,
**who** are looking for an entertaining first contact with the Computer Science department,
**Pac-Party is** a browser-based multiplayer game,
**that** lets up to 5 visitors compete against each other - no app download, just scan a QR code and start playing.

---

## 2. Business Goals

- **Crowd Magnet:** Attract fair visitors to the booth through an interactive game
- **Low Entry Barrier:** Instant game start without app installation or account
- **High Rotation:** Short rounds (2-3 min) allow many visitors to participate
- **Brand Building:** Positive first impression of the Computer Science department

---

## 3. Target Audience

| Role | Description | Need |
|------|-------------|------|
| **Players** | Fair visitors (primarily prospective students) | Have fun, be able to play quickly |
| **Spectators** | Passersby attracted by the screen | Be entertained, understand what's happening |
| **Booth Staff** | Department employees | Game runs autonomously, no explanation needed |

---

## 4. Technical Architecture

### 4.1 System Overview

```
[Mobile Browser] ←WebSocket→ [Node.js Server] ←→ [TV Display Browser]
     (Controller)                (Game Engine)        (Visualization)
```

### 4.2 Technology Stack

| Layer | Technology | Rationale |
|-------|------------|-----------|
| **Backend** | Node.js | JavaScript everywhere, excellent for real-time |
| **Communication** | WebSockets | Real-time bidirectional communication |
| **TV Display** | HTML5 Canvas | 2D graphics, runs in any browser |
| **Mobile Controller** | Responsive HTML | Touch interface, universal compatibility |
| **Hosting** | Local Server | No internet dependency, full control |

### 4.3 Network Architecture

```
[Laptop Server] ←LAN→ [Router] ←WiFi→ [Mobile Devices]
                                  ↓
                              [TV Display]
```

**Benefits:**
- No dependency on trade show WiFi
- Controlled environment
- Low latency for real-time gameplay

### 4.4 Data Flow

1. **Player joins:** QR scan → WebSocket connection → Role assignment
2. **Game input:** Touch → WebSocket → Server validation → Broadcast
3. **Game state:** Server → All clients (real-time synchronization)
4. **Collision detection:** Server-side (authoritative)

---

## 5. Scope

### In Scope (What we build)

| Area | Details | Technical Implementation |
|------|---------|-------------------------|
| **Big Screen** | Game field, Timer, Score, QR Code, Logo, Highscore | HTML5 Canvas + WebSocket client |
| **Phone Controller** | D-Pad controls, Role display, Game status | Responsive HTML + Touch events |
| **Game Mechanics** | Classic Pac-Man: eat dots, Power Pellets | Server-side game engine |
| **Lobby System** | QR Code entry, 5 player slots, Queue | WebSocket connection management |
| **Round Logic** | 2-3 minute timer, Game Over conditions | Server-controlled state machine |
| **Feedback** | Sound effects (Screen), Vibration (Controller) | Web Audio API + Vibration API |
| **Network** | Local network (own router + server laptop) | Local WiFi hotspot |

### Out of Scope (What we deliberately DON'T build)

| Exclusion | Rationale | Technical Note |
|-----------|-----------|----------------|
| Login / Accounts | Barrier for quick entry | No user database needed |
| Chat Function | Unnecessary - players stand next to each other | No messaging system |
| Persistent Data | Only daily highscore, nothing permanently stored | In-memory storage only |
| Native Mobile App | Web-based is sufficient, no App Store needed | Browser-only solution |
| Multiple Levels/Maps | One classic maze is enough for fair context | Single game map |
| Tournament Mode | Overkill for spontaneous fair visitors | Simple session-based games |

---

## 6. Constraints & Risks

### Constraints

- **Network:** Trade show WiFi is unreliable → own local network required
- **Hardware:** Requires large screen/projector + laptop as server + router
- **Self-explanatory:** Must work without instruction (no permanent booth staff)
- **Browser Compatibility:** Must run on iOS Safari and Android Chrome

### Technical Risks & Mitigations

| Risk | Impact | Technical Mitigation |
|------|--------|---------------------|
| **Real-time Sync Issues** | Players see different game states | Server-authoritative architecture |
| **Mobile Browser Compatibility** | Controller doesn't work on some phones | Test on iOS Safari + Android Chrome |
| **WebSocket Disconnects** | Players drop out during game | Automatic reconnection + queue management |
| **Canvas Performance** | Laggy display on older hardware | 60fps optimization + fallback rendering |
| **Network Configuration** | QR code points to wrong IP | Automatic IP detection + manual override |

---

## 7. Roadmap (Epics + Technical Architecture)

| # | Epic | Business Value | Technical Focus |
|---|------|----------------|-----------------|
| **1** | **Lobby & Entry** | Minimizes time from "passing by" to "playing" | WebSocket connections + QR generation |
| **2** | **Gameplay (Core)** | The heart - without working Pac-Man no game | Game engine + collision detection |
| **3** | **Mobile Controller** | Enables intuitive control, eyes stay on big screen | Touch input + responsive design |
| **4** | **Display (Big Screen)** | The "wow factor" - attracts spectators, shows everything important | Canvas rendering + real-time updates |
| **5** | **Setup & Deployment** | Easy installation at the booth | One-click scripts + documentation |

---

## 8. Implementation Timeline

### Sprint Plan (4 weeks)

| Sprint | Duration | Focus | Deliverable |
|--------|----------|-------|-------------|
| **Sprint 1** | Week 1 | Foundation & Learning | Basic server + simple game field |
| **Sprint 2** | Week 2 | Core Gameplay | Movement + point collection |
| **Sprint 3** | Week 3 | Multiplayer | 5 players simultaneously |
| **Sprint 4** | Week 4 | Trade Show Ready | Robust + self-explanatory |

**Total Effort:** ~50 hours over 4 weeks (~12h/week)

---

## 9. Success Metrics

| Metric | Goal | Technical KPI |
|--------|------|---------------|
| Time to start playing | < 30 seconds (QR scan to lobby) | WebSocket connection < 2s |
| Average round duration | 2-3 minutes | Timer accuracy ±1s |
| Player rotation per hour | 20+ different players | System uptime > 99% |
| Understandability | Players need no explanation from staff | Error rate < 5% |
| **Technical Stability** | **8h continuous operation** | **No crashes, memory leaks** |

---

## 10. Quality Standards

### Definition of Done
- ✅ Browser compatibility (iOS Safari + Android Chrome)
- ✅ 5-player multiplayer without lag
- ✅ 8h continuous operation
- ✅ One-click deployment scripts
- ✅ Comprehensive troubleshooting documentation

### Architecture Principles
- **Server-authoritative:** All game logic runs on server
- **Fail-safe:** System recovers from disconnections
- **Self-contained:** No external dependencies
- **Student-operable:** Others can run it without developer

---

## 11. Learning Resources

**For JavaScript/Node.js transition:**
- Node.js Crash Course (Traversy Media)
- Modern JavaScript Tutorial (javascript.info)
- Real-time Multiplayer Games with Socket.io

**Ready for Phase 3: Implementation** 🚀
