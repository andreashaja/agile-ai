# Backlog Refinement

**Purpose:** Capture ideas that emerge during sprints for future consideration.

This document collects feature requests, improvements, and ideas that come up during development but are **not part of the current sprint**. These items will be reviewed before each new sprint to decide if they should be added to the Product Backlog.

---

## How to Use This Document

When the user suggests a new feature during a sprint:
1. **Acknowledge** the idea positively
2. **Add it here** with context
3. **Continue** with the current sprint goal
4. **Review** before next sprint planning

---

## Captured Ideas

### Idea 1: Dynamic QR Code with IP Detection

| Field | Value |
|-------|-------|
| **Captured During** | Sprint 1.1 |
| **Date** | 2025-12-20 |
| **Suggested By** | Agent |
| **Related Epic** | Epic 1: Lobby & Einstieg |

**Description:**
Currently, users must manually type the server URL on their phone. The QR code feature from Story 1.1 requires automatic IP detection to generate a QR code that works across different network setups.

**Potential Value:**
Dramatically reduces friction for new players joining the game. No typing required.

**Initial Complexity Estimate:**
Medium - Need to detect local IP across Mac/Windows/Linux, handle edge cases (multiple network interfaces, VPN).

**Status:** Pending Review

---

### Idea 2: Mobile Viewport Optimization

| Field | Value |
|-------|-------|
| **Captured During** | Sprint 1.1 |
| **Date** | 2025-12-20 |
| **Suggested By** | Agent |
| **Related Epic** | Epic 3: Mobile Controller |

**Description:**
The controller page works on mobile but could be better optimized. Adding proper viewport meta tags and CSS would prevent zooming issues and make buttons fill the screen better.

**Potential Value:**
Better user experience on mobile. Buttons easier to hit without looking.

**Initial Complexity Estimate:**
Low - Just CSS and meta tag changes.

**Status:** Pending Review

---

### Idea 3: Sound Toggle Button

| Field | Value |
|-------|-------|
| **Captured During** | Sprint 1.2 |
| **Date** | 2025-12-21 |
| **Suggested By** | User |
| **Related Epic** | Epic 2: Gameplay |

**Description:**
User asked: "Can we add a mute button? At the trade show it might get loud and we want to turn off game sounds quickly."

**Potential Value:**
Important for trade show environment. Quick toggle without going into settings.

**Initial Complexity Estimate:**
Low - Simple UI button + audio context control.

**Status:** Added to Backlog (Story 2.5 extended)

---

### Idea 4: Spectator Count Display

| Field | Value |
|-------|-------|
| **Captured During** | Sprint 1.2 |
| **Date** | 2025-12-21 |
| **Suggested By** | User |
| **Related Epic** | Epic 4: Display |

**Description:**
User asked: "Can we show how many people are watching? Like 'X spectators viewing'?"

**Potential Value:**
Creates social proof, encourages more people to join when they see others are watching.

**Initial Complexity Estimate:**
Low - Already track connections, just need to display count.

**Status:** Pending Review

---

## Review History

| Date | Sprint | Ideas Reviewed | Outcome |
|------|--------|----------------|---------|
| 2025-12-21 | Before Sprint 1.2 | QR Code, Viewport | Deferred - focus on core gameplay first |
| 2025-12-22 | Before Sprint 1.3 | Sound Toggle, Spectator Count | Sound Toggle added to Backlog |

---

## Notes

- Ideas marked "Pending Review" will be discussed before the next sprint
- "Added to Backlog" means the idea was formally added to the Product Backlog
- "Deferred" means we'll reconsider later
- "Rejected" means we decided not to pursue (with reason documented)
- The QR Code feature is high priority but requires research - may become Sprint 2.x focus
