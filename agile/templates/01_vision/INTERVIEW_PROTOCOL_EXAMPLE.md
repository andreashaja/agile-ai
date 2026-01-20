# Interview Protocol: Vision Phase

**Started:** Sat Jan 17 2026, 10:00 AM
**Status:** Complete

## Progress Tracking

| Step | Name | Status | Started | Completed | Notes |
|------|------|--------|---------|-----------|-------|
| 1 | EXPLORE | [x] Complete | 10:01 AM | 10:08 AM | Brain dump complete, user confirmed |
| 2 | DEFINE | [x] Complete | 10:08 AM | 10:12 AM | Pitch & Scope confirmed |
| 3 | STRUCTURE | [x] Complete | 10:12 AM | 10:16 AM | 4 Epics confirmed |
| 4 | DETAIL | [x] Complete | 10:16 AM | 10:22 AM | 19 Stories across 4 Epics |
| 5 | VALIDATE | [x] Complete | 10:22 AM | 10:28 AM | INVEST passed, artifacts generated |

## Conversation Log

### Step 1: EXPLORE (Complete)

**User's Initial Input:**
> I want to build a multiplayer Pac-Man game. It should run at a university trade fair where visitors pass by our booth. Kind of like a honeypot to attract people.

**Clarifying Questions & Answers:**

| Topic | Question | Answer |
|-------|----------|--------|
| Setup | Large screen + phone controllers? | Yes, exactly |
| Players | How many simultaneously? | 5 (1 Pac-Man, 4 Ghosts) |
| Game Principle | Classic or variant? | Classic |
| Round Time | Quick rounds? | Yes, 2-3 minutes |
| Context | What does the booth present? | Computer Science department, attract prospective students |
| Entry | How do players join? | Scan QR code, web-based without app |
| Queue | What if a 6th person wants to play? | Waiting queue with auto-fill |
| Branding | Department reference? | Integrate logo |
| Operation | Staff needed? | No, self-explanatory |
| Network | WiFi or local? | Local network (own router) |
| Game End | When does round end? | Time expired OR Pac-Man caught |
| After Round | Same players or new? | New lobby, so new people can join |
| Fill-in | On disconnect? | Yes, from waiting queue |
| Extras | Special wishes? | Sound effects, daily highscore list |
| Exclusions | What NOT? | No login, no accounts, no chat |

**User Confirmation:** "Perfect! All captured correctly."

---

### Step 2: DEFINE (Complete)

**Elevator Pitch (Confirmed):**
> **For** prospective students at university trade fairs,
> **who** are looking for an entertaining first contact with the Computer Science department,
> **Pac-Party is** a browser-based multiplayer game,
> **that** allows up to 5 visitors to compete simultaneously - no app download, just scan QR code and start playing.

**Target Audience:**
- Players (trade fair visitors, primarily prospective students)
- Spectators (passersby attracted by the screen)
- Booth Staff (monitors, but doesn't need to explain)

**Scope IN:**
- Large screen: Game field, timer, score, QR code, logo
- Phone controller: D-Pad, role indicator, lobby status
- Game mechanics: Classic Pac-Man with power pellets
- Lobby system: QR entry, 5 slots, waiting queue, auto-fill
- Round logic: 2-3 min, ends on timeout/catch, new lobby
- Extras: Sound effects, daily highscore
- Network: Local (own router)

**Scope OUT:**
- Login/Accounts, Chat, Persistent Data, Native App, Multiple Levels, Tournament Mode

**User Confirmation:** "Perfect!"

---

### Step 3: STRUCTURE (Complete)

**Initial Proposal:** 5 Epics (Lobby, Gameplay, Controller, Display, Extras)

**User Feedback:** Remove Epic 5 (Extras), integrate sounds/highscore into other Epics

**Final Epics (4):**

| # | Epic | Business Value | Integrated Extras |
|---|------|----------------|-------------------|
| 1 | Lobby & Entry | Minimizes time to start playing | Highscore motivation |
| 2 | Gameplay (Core) | Heart of the game | Sound effects |
| 3 | Mobile Controller | Intuitive control | - |
| 4 | Display (Screen) | Wow factor, attracts spectators | Logo, highscore list |

**User Confirmation:** "Perfect!"

---

### Step 4: DETAIL (Complete)

**Epic 1: Lobby & Entry (5 Stories)**
| # | Story | Acceptance Criteria |
|---|-------|---------------------|
| 1.1 | Scan QR code → join game instantly | QR code visible, opens web app |
| 1.2 | Automatic role assignment | First = Pac-Man, rest = Ghosts |
| 1.3 | Waiting queue when lobby full | Shows "You are #X in queue" |
| 1.4 | Auto-fill on disconnect | Waiting player fills in automatically |
| 1.5 | See highscore before playing | Highscore visible in lobby |

**Epic 2: Gameplay (5 Stories)**
| # | Story | Acceptance Criteria |
|---|-------|---------------------|
| 2.1 | Collect dots for score | Dots on field, score counts up |
| 2.2 | Power pellets → chase ghosts | Power mode ~10 sec |
| 2.3 | Ghost catches Pac-Man → round ends | Collision = Ghosts win |
| 2.4 | Automatic round end after 2-3 min | Timer expires → end |
| 2.5 | Sound effects on events | Sounds on dot, power, catch, end |

**Epic 3: Mobile Controller (4 Stories)**
| # | Story | Acceptance Criteria |
|---|-------|---------------------|
| 3.1 | Large D-Pad buttons | Touch buttons usable without looking |
| 3.2 | Role indicator (color) | Yellow = Pac-Man, Ghosts = Red/Pink/Cyan/Orange |
| 3.3 | Game status on phone | Lobby/Game/Queue recognizable |
| 3.4 | Haptic feedback (vibration) | Vibration on catch, power, end |

**Epic 4: Display (5 Stories)**
| # | Story | Acceptance Criteria |
|---|-------|---------------------|
| 4.1 | Visually appealing game field | Classic maze, high-contrast colors |
| 4.2 | QR code always visible | Permanently visible for spontaneous joining |
| 4.3 | Timer & score display | Large display for spectators |
| 4.4 | Department logo | Subtle but visible |
| 4.5 | Daily highscore list | Top 5-10 scores displayed |

**Summary:** 4 Epics, 19 User Stories total

**User Confirmation:** "Perfect! Those are all stories."

---

### Step 5: VALIDATE (Complete)

**INVEST Check Results:**

| Criterion | Status | Notes |
|-----------|--------|-------|
| **I**ndependent | PASS | All stories can be implemented standalone |
| **N**egotiable | PASS | No technical constraints, only user goals |
| **V**aluable | PASS | Every story has "so that..." justification |
| **E**stimable | PASS | Stories are concrete enough for estimation |
| **S**mall | PASS | No story is too large for one sprint |
| **T**estable | PASS | All stories have testable acceptance criteria |

**Completion Checklist:**

- [x] Product Goal exists (Elevator Pitch)
- [x] Target Audience defined (Players, Spectators, Booth Staff)
- [x] Scope boundaries documented (IN & OUT)
- [x] 3-5 Epics with Business Value (4 Epics)
- [x] 3-5 Stories per Epic (4-5 per Epic, 19 total)
- [x] No open "TBD" placeholders
- [x] All stories pass INVEST
- [x] User has confirmed each section

**Generated Artifacts:**
1. `PROJECT_VISION.md` - Elevator Pitch, Target Audience, Scope, Roadmap
2. `PRODUCT_BACKLOG.md` - 4 Epics with 19 User Stories

**User called `/visionary-complete` at 10:28 AM**
