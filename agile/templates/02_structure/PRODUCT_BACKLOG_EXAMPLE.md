# Product Backlog v2: Pac-Party

**Status:** Architecture Complete - Technical Enhancement
**Focus:** User Needs + Technical Implementation
**Version:** 2.0 (Enhanced with Technical Enablers)

---

## Introduction

This enhanced backlog combines the **User Stories** from Phase 1 with the **Technical Enabler Stories** required for implementation.

**Legend:**
- **User Stories:** Original features from the Vision
- **[TECH-ENABLER]:** Technical infrastructure tasks
- **[ARCH-ADD]:** New technical stories from the Architecture phase

---

## Epic 1: Lobby & Entry

**Business Value:** Minimizes time from "passing by" to "playing" - the faster the entry, the more visitors will try it out.

### [TECH-ENABLER] 1.0: WebSocket Connection Management

- **As a** System
- **I need to** manage WebSocket connections,
- **so that** players can connect and disconnect.

*Rationale:* Foundation for all multiplayer features
*Acceptance Criteria:*
- [ ] Server accepts WebSocket connections
- [ ] Connection drops are detected
- [ ] Automatic cleanup on disconnect

### Story 1.1: QR Code Entry

- **As a** Visitor
- **I want to** scan a QR code on the large screen,
- **so that** I can instantly join the game without typing a URL.

*Acceptance Criteria:*
- [ ] QR code is clearly visible on the large screen
- [ ] Scanning opens the web app directly in mobile browser
- [ ] No app installation required

### Story 1.2: Automatic Role Assignment

- **As a** Visitor
- **I want to** be automatically assigned a role (Pac-Man or Ghost),
- **so that** I don't have to choose or discuss with others.

*Acceptance Criteria:*
- [ ] First player in lobby becomes Pac-Man
- [ ] Players 2-5 become Ghosts (Red, Pink, Cyan, Orange)
- [ ] Assignment happens automatically without user interaction

### Story 1.3: Queue for Full Lobby

- **As the** 6th visitor (or later)
- **I want to** be placed in a queue,
- **so that** I know I'm next in line.

*Acceptance Criteria:*
- [ ] When lobby is full (5 players), "Lobby Full" message appears
- [ ] Waiting players see their position: "You are #1 in queue"
- [ ] Position updates automatically

### Story 1.4: Auto-Join on Disconnect

- **As a** Waiting player
- **I want to** automatically join when someone disconnects,
- **so that** the game always has full players.

*Acceptance Criteria:*
- [ ] When a player disconnects, first person from queue joins
- [ ] Joining happens automatically without manual action
- [ ] New player receives the freed role

### Story 1.5: Highscore Motivation in Lobby

- **As a** Visitor
- **I want to** see the current highscore before playing,
- **so that** I'm motivated to beat it.

*Acceptance Criteria:*
- [ ] Daily highscore is visible in lobby/waiting view
- [ ] Shows at least the top score

### [TECH-ENABLER] 1.6: QR Code Generation

- **As a** System
- **I need to** generate dynamic QR codes,
- **so that** players get the correct URL to join.

*Rationale:* QR code must point to current server IP
*Acceptance Criteria:*
- [ ] QR code points to local server IP
- [ ] Code is generated at server start
- [ ] Works even if IP changes

---

## Epic 2: Gameplay (Core)

**Business Value:** The heart of the game - without working Pac-Man there is no experience at the booth.

### [TECH-ENABLER] 2.0: Game State Synchronization

- **As a** System
- **I need to** keep game state synchronized between all clients,
- **so that** all players see the same thing.

*Rationale:* Core of multiplayer gameplay
*Acceptance Criteria:*
- [ ] Player positions are transmitted in real-time
- [ ] Collision detection runs on server
- [ ] All clients receive identical updates

### Story 2.1: Collecting Points

- **As** Pac-Man
- **I want to** collect dots,
- **so that** I can build a score and chase the highscore.

*Acceptance Criteria:*
- [ ] Dots are distributed across the playing field
- [ ] When collected, dot disappears and score increases
- [ ] Score is displayed in real-time

### Story 2.2: Power Pellets

- **As** Pac-Man
- **I want to** eat Power Pellets,
- **so that** I can chase the ghosts for a short time.

*Acceptance Criteria:*
- [ ] Power Pellets are larger/different from normal dots
- [ ] After collecting: Power mode for ~10 seconds
- [ ] Ghosts become "edible" in power mode (visually indicated)
- [ ] Pac-Man can catch ghosts in power mode (bonus points)

### Story 2.3: Ghost Catches Pac-Man

- **As a** Ghost
- **I want to** be able to catch Pac-Man,
- **so that** I win the game for the Ghost team.

*Acceptance Criteria:*
- [ ] Collision Ghost + Pac-Man (outside power mode) = Round ends
- [ ] Ghosts win, Pac-Man loses
- [ ] Game Over is clearly displayed

### Story 2.4: Automatic Round End (Timer)

- **As a** Player
- **I want** the round to automatically end after 2-3 minutes,
- **so that** new visitors get a turn.

*Acceptance Criteria:*
- [ ] Countdown timer runs from start (2-3 min configurable)
- [ ] Round ends automatically when timer expires
- [ ] Pac-Man wins if timer expires (survived)
- [ ] After: New lobby for new players

### Story 2.5: Sound Effects

- **As a** Player
- **I want to** hear audio feedback on important events,
- **so that** the game feels alive.

*Acceptance Criteria:*
- [ ] Sound on: Collecting dot
- [ ] Sound on: Collecting Power Pellet
- [ ] Sound on: Catching ghost (in power mode)
- [ ] Sound on: Pac-Man caught (Game Over)
- [ ] Sound on: Round end (timer expired)

### [ARCH-ADD] 2.6: Collision Detection Engine

- **As a** System
- **I need to** detect collisions between players and objects,
- **so that** gameplay rules work.

*Rationale:* Pac-Man eats dots, Ghosts catch Pac-Man
*Acceptance Criteria:*
- [ ] Pac-Man + Dot = Dot disappears, Score +10
- [ ] Pac-Man + Ghost = Game Over (except in power mode)
- [ ] Pac-Man + Power Pellet = Power mode activated

---

## Epic 3: Mobile Controller

**Business Value:** Enables intuitive control from phone - must be usable without looking so players can watch the big screen.

### [TECH-ENABLER] 3.0: Touch Input Handling

- **As a** System
- **I need to** convert touch events into movement commands,
- **so that** phone control works.

*Rationale:* Bridge between touch screen and game engine
*Acceptance Criteria:*
- [ ] Touch on "Up" button → "up" command to server
- [ ] Prevents multiple inputs (debouncing)
- [ ] Works on iOS Safari and Android Chrome

### Story 3.1: Large D-Pad Buttons

- **As a** Player
- **I want** large directional buttons on my phone,
- **so that** I can control without looking at my phone.

*Acceptance Criteria:*
- [ ] Four large touch buttons: Up, Down, Left, Right
- [ ] Buttons are large enough for thumb operation
- [ ] Visual feedback on touch (button press)

### Story 3.2: Role Display (Color Coding)

- **As a** Player
- **I want to** see on my phone which role I have,
- **so that** I can find myself on the big screen.

*Acceptance Criteria:*
- [ ] Controller background shows role color
- [ ] Pac-Man = Yellow
- [ ] Ghosts = Red, Pink, Cyan, Orange (depending on assignment)
- [ ] Color is immediately recognizable

### Story 3.3: Game Status Display

- **As a** Player
- **I want to** see the current game status on my phone,
- **so that** I know if I'm in lobby, in game, or in queue.

*Acceptance Criteria:*
- [ ] Status "Waiting for players..." in lobby
- [ ] Status "Game running!" during game
- [ ] Status "You are #X in queue" when waiting
- [ ] Status updates automatically

### Story 3.4: Haptic Feedback (Vibration)

- **As a** Player
- **I want to** feel haptic feedback on important events,
- **so that** I notice game events without looking at my phone.

*Acceptance Criteria:*
- [ ] Vibration on: Being caught (as Pac-Man or Ghost)
- [ ] Vibration on: Power mode start
- [ ] Vibration on: Round end
- [ ] Vibration works on common mobile browsers

---

## Epic 4: Display (Big Screen)

**Business Value:** The "wow factor" - attracts spectators from afar and shows everything important for players and audience.

### [TECH-ENABLER] 4.0: Canvas Rendering Engine

- **As a** System
- **I need to** render the playing field on HTML5 Canvas,
- **so that** spectators can see the game.

*Rationale:* Visualization of game state
*Acceptance Criteria:*
- [ ] 60 FPS rendering without stuttering
- [ ] Scales to different screen sizes
- [ ] Draws Pac-Man, Ghosts, Dots, Walls

### Story 4.1: Visually Appealing Game Field

- **As a** Spectator
- **I want to** see a visually appealing game field,
- **so that** I'm attracted to the booth.

*Acceptance Criteria:*
- [ ] Classic Pac-Man maze design
- [ ] Clearly recognizable characters (Pac-Man, 4 Ghosts)
- [ ] High-contrast colors (visible from distance)
- [ ] Dots and Power Pellets clearly distinguishable

### Story 4.2: QR Code Permanently Visible

- **As a** Spectator
- **I want to** see the QR code prominently on screen,
- **so that** I can spontaneously join.

*Acceptance Criteria:*
- [ ] QR code is permanently visible (corner or overlay)
- [ ] Large enough to scan from 1-2 meters distance
- [ ] Visible during game (not just in lobby)

### Story 4.3: Timer & Score Display

- **As a** Spectator
- **I want to** see timer and current score,
- **so that** I can follow the game progress.

*Acceptance Criteria:*
- [ ] Countdown timer displayed large and prominently
- [ ] Current Pac-Man score visible
- [ ] Readable from several meters away

### Story 4.4: Department Logo

- **As** Booth staff
- **I want** the department logo on the screen,
- **so that** it's clear who's behind the game.

*Acceptance Criteria:*
- [ ] Logo is visible but subtle (doesn't disturb gameplay)
- [ ] Position: Corner or header area
- [ ] Correct rendering of official logo

### Story 4.5: Daily Highscore List

- **As a** Spectator
- **I want to** see the daily highscore list,
- **so that** I know what score to beat.

*Acceptance Criteria:*
- [ ] Top 5-10 highscores of the day displayed
- [ ] Shows score (no name needed, since no accounts)
- [ ] Visible in lobby phase or as overlay
- [ ] List updates when new highscore is set

---

## Epic 5: Setup & Deployment [ARCH-ADD]

**Business Value:** Enables easy installation at the booth without technical know-how

### [TECH-ENABLER] 5.1: Local Server Setup

- **As** Booth staff
- **I want to** start the server with one click,
- **so that** the game runs without technical know-how.

*Rationale:* Other students must be able to operate the system
*Acceptance Criteria:*
- [ ] start.sh/start.bat script
- [ ] Automatic dependency installation
- [ ] Clear error messages on problems

### [TECH-ENABLER] 5.2: Network Configuration

- **As a** System
- **I need to** automatically detect the local IP address,
- **so that** the QR code points to the correct address.

*Rationale:* Router setup can have different IP ranges
*Acceptance Criteria:*
- [ ] Detects local IP automatically
- [ ] Works with different router setups
- [ ] Fallback to localhost if needed

---

## Icebox (Potential Extensions)

*Not in current scope, but possible for later:*

- **Spectator Mode:** Spectators can follow game on their own phone
- **Leaderboard with Names:** Players can optionally enter a name
- **Multiple Maps:** Different maze layouts for variety
- **Custom Branding:** Customizable colors/logos for other departments
- **Statistics Dashboard:** How many players/rounds per day

---

## Summary

**Original User Stories:** 17
**Added Technical Enablers:** 7
**New Epics:** 1 (Setup & Deployment)
**Total Backlog Items:** 24

**All original User Stories have been preserved and only extended with technical infrastructure.**
