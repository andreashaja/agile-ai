# Product Backlog: Pac-Party

**Status:** Inception Complete
**Focus:** User Needs & Functional Requirements

---

## Introduction

This backlog defines the features for a multiplayer Pac-Man game at a university trade fair. The focus is on the **User Experience** of players (trade fair visitors) and spectators (passersby).

Items are grouped by **Epics** (thematic areas) with clear Business Value.

---

## Epic 1: Lobby & Entry

**Business Value:** Minimizes the time from "walking by" to "playing" - the faster the entry, the more visitors try it out.

### Story 1.1: QR Code Entry

- **As a** visitor
- **I want to** scan a QR code on the large screen,
- **so that** I can join the game instantly without typing a URL.

*Acceptance Criteria:*
- [ ] QR code is clearly visible on the large screen
- [ ] Scanning opens the web app directly in the mobile browser
- [ ] No app installation required

### Story 1.2: Automatic Role Assignment

- **As a** visitor
- **I want to** be automatically assigned a role (Pac-Man or Ghost),
- **so that** I don't have to choose or discuss with others.

*Acceptance Criteria:*
- [ ] First player in the lobby becomes Pac-Man
- [ ] Players 2-5 become Ghosts (Red, Pink, Cyan, Orange)
- [ ] Assignment happens automatically without user interaction

### Story 1.3: Waiting Queue When Lobby Is Full

- **As a** 6th visitor (or later)
- **I want to** be placed in a waiting queue,
- **so that** I know I'm next in line.

*Acceptance Criteria:*
- [ ] When lobby is full (5 players), "Lobby full" appears
- [ ] Waiting players see their position: "You are #1 in the queue"
- [ ] Position updates automatically

### Story 1.4: Auto-Fill on Disconnect

- **As a** waiting player
- **I want to** automatically move up when someone disconnects,
- **so that** the game always stays fully occupied.

*Acceptance Criteria:*
- [ ] On player disconnect, first person from queue fills in
- [ ] Fill-in happens automatically without manual action
- [ ] Filled-in player gets the vacated role

### Story 1.5: Highscore Motivation in Lobby

- **As a** visitor
- **I want to** see the current highscore before playing,
- **so that** I'm motivated to beat it.

*Acceptance Criteria:*
- [ ] Daily highscore is visible in lobby/waiting view
- [ ] Shows at least the top score

---

## Epic 2: Gameplay (Core)

**Business Value:** The heart of the game - without working Pac-Man, there's no experience at the booth.

### Story 2.1: Collect Dots

- **As** Pac-Man
- **I want to** collect dots,
- **so that** I can build up a score and chase the highscore.

*Acceptance Criteria:*
- [ ] Dots are distributed across the game field
- [ ] When collected, dot disappears and score increases
- [ ] Score is displayed in real-time

### Story 2.2: Power Pellets

- **As** Pac-Man
- **I want to** eat power pellets,
- **so that** I can chase ghosts for a short time.

*Acceptance Criteria:*
- [ ] Power pellets are larger/differently displayed than normal dots
- [ ] After collection: Power mode for ~10 seconds
- [ ] Ghosts become "edible" in power mode (visually recognizable)
- [ ] Pac-Man can catch ghosts in power mode (bonus points)

### Story 2.3: Ghost Catches Pac-Man

- **As a** Ghost
- **I want to** catch Pac-Man,
- **so that** I win the game for the Ghost team.

*Acceptance Criteria:*
- [ ] Collision Ghost + Pac-Man (outside power mode) = round ends
- [ ] Ghosts win, Pac-Man loses
- [ ] Game Over is clearly displayed

### Story 2.4: Automatic Round End (Timer)

- **As a** player
- **I want** the round to automatically end after 2-3 minutes,
- **so that** new visitors can have a turn.

*Acceptance Criteria:*
- [ ] Countdown timer runs from start (2-3 min configurable)
- [ ] When expired, round ends automatically
- [ ] Pac-Man wins if timer expires (survived)
- [ ] After: New lobby for new players

### Story 2.5: Sound Effects

- **As a** player
- **I want to** hear audio feedback on important events,
- **so that** the game feels alive.

*Acceptance Criteria:*
- [ ] Sound on: Dot collected
- [ ] Sound on: Power pellet collected
- [ ] Sound on: Ghost caught (in power mode)
- [ ] Sound on: Pac-Man caught (Game Over)
- [ ] Sound on: Round end (timer expired)

---

## Epic 3: Mobile Controller

**Business Value:** Enables intuitive control from phone - must be usable without looking, so players can watch the large screen.

### Story 3.1: Large D-Pad Buttons

- **As a** player
- **I want to** have large directional buttons on my phone,
- **so that** I can steer without looking at my phone.

*Acceptance Criteria:*
- [ ] Four large touch buttons: Up, Down, Left, Right
- [ ] Buttons are large enough for thumb operation
- [ ] Visual feedback on touch (button press)

### Story 3.2: Role Indicator (Color Coding)

- **As a** player
- **I want to** see on my phone which role I have,
- **so that** I can find myself on the large screen.

*Acceptance Criteria:*
- [ ] Controller background shows role color
- [ ] Pac-Man = Yellow
- [ ] Ghosts = Red, Pink, Cyan, Orange (depending on assignment)
- [ ] Color is immediately recognizable

### Story 3.3: Game Status Display

- **As a** player
- **I want to** see the current game status on my phone,
- **so that** I know if I'm in the lobby, in-game, or in the queue.

*Acceptance Criteria:*
- [ ] Status "Waiting for players..." in lobby
- [ ] Status "Game running!" during game
- [ ] Status "You are #X in the queue" when waiting
- [ ] Status updates automatically

### Story 3.4: Haptic Feedback (Vibration)

- **As a** player
- **I want to** feel haptic feedback on important events,
- **so that** I notice game events without looking at my phone.

*Acceptance Criteria:*
- [ ] Vibration on: Being caught (as Pac-Man or Ghost)
- [ ] Vibration on: Power mode start
- [ ] Vibration on: Round end
- [ ] Vibration works on common mobile browsers

---

## Epic 4: Display (Large Screen)

**Business Value:** The "wow factor" - attracts spectators from afar and shows everything important for players and audience.

### Story 4.1: Visually Appealing Game Field

- **As a** spectator
- **I want to** see a visually appealing game field,
- **so that** I'm attracted to the booth.

*Acceptance Criteria:*
- [ ] Classic Pac-Man maze design
- [ ] Well-recognizable characters (Pac-Man, 4 Ghosts)
- [ ] High-contrast colors (visible from distance)
- [ ] Dots and power pellets clearly distinguishable

### Story 4.2: QR Code Permanently Visible

- **As a** spectator
- **I want to** see the QR code large on the screen,
- **so that** I can spontaneously join.

*Acceptance Criteria:*
- [ ] QR code is permanently visible (corner or overlay)
- [ ] Large enough to scan from 1-2 meter distance
- [ ] Also visible during game (not just in lobby)

### Story 4.3: Timer & Score Display

- **As a** spectator
- **I want to** see timer and current score,
- **so that** I can follow the game progress.

*Acceptance Criteria:*
- [ ] Countdown timer large and prominently displayed
- [ ] Current Pac-Man score visible
- [ ] Readable from several meters away

### Story 4.4: Department Logo

- **As** booth staff
- **I want to** see the department logo on the screen,
- **so that** it's clear who's behind the game.

*Acceptance Criteria:*
- [ ] Logo is visible but subtle (doesn't disturb gameplay)
- [ ] Position: Corner or header area
- [ ] Correct display of official logo

### Story 4.5: Daily Highscore List

- **As a** spectator
- **I want to** see the daily highscore list,
- **so that** I know what score I need to beat.

*Acceptance Criteria:*
- [ ] Top 5-10 highscores of the day displayed
- [ ] Shows score (no name needed, since no accounts)
- [ ] Visible in lobby phase or as overlay
- [ ] List updates when new highscore is set

---

## Icebox (Potential Extensions)

*Not in current scope, but conceivable for later:*

- **Spectator Mode:** Spectators can follow game on their own phone
- **Leaderboard with Names:** Players can optionally enter a name
- **Multiple Maps:** Different maze layouts for variety
- **Custom Branding:** Customizable colors/logos for other departments
- **Statistics Dashboard:** How many players/rounds per day
