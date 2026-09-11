# LOCAL CRICKET LEAGUE

A local cricket tournament management platform
with real-time player auctions.

MAIN USERS:

1. Player
2. Team Owner
3. Organizer
4. Admin

CORE TECHNOLOGY:

Frontend:
Next.js + TypeScript

UI:
Tailwind CSS + shadcn/ui

Backend:
Next.js server-side logic

Database:
Supabase PostgreSQL

Authentication:
Supabase Auth

Storage:
Supabase Storage

Realtime:
Supabase Realtime

Deployment:
Vercel



# Local Cricket Platform — Product Requirements & Feature Specification

### 1. Player Profiles & Registration
- Self-Service Onboarding: Collects personal details, playing role (Batter, Fast Bowler, Spin Bowler, All-Rounder, Wicketkeeper), batting hand, bowling style, and contact info.
- Cricketing CV & Match Records: Past league stats, career highlights, strike rates, and bowling averages for owner evaluation.
- Document Verification (KYC): ID or residency document uploads to prevent identity fraud and unauthorized ringers.
- Media Showcase: Player headshots, profile photos, and external links to match highlight reels.
- Availability & Base Price: Round availability declarations, jersey sizes, and base price tier selection.

---

### 2. Organizer Dashboard & Verification
- Review & Approval Queue: Central admin screen to approve, reject, or request changes on player registrations.
- Auction Category Sets: Tool to group players into sequential bidding sets (e.g., Marquee, Batsmen Set 1, Fast Bowlers, Emerging Players).
- System Audit Logs: Tracks admin approvals, base price overrides, and manual purse balance corrections.

---

### 3. Real-Time Player Auction Engine
- Auctioneer Console: Master controls to present players, start timers, declare SOLD/UNSOLD, announce bids, or pause the room.
- Single-Player Focus Room: Synchronized display showing current player details, base price, current high bidder, and next valid increment.
- Dynamic Bid Increments: Automated minimum raise amounts determined by current price brackets.
- Server-Side Purse Guard: Automatically blocks bids if a team cannot afford their remaining minimum squad quota.
- Accelerated Re-Auction Pool: Unsold players automatically route to a secondary round with optional base price markdowns.
- Complete Bid Ledger: Millisecond-precision historical log of every placed bid, bidder ID, and timestamp.

---

### 4. Real-Time Bidding Infrastructure & Anti-Cheating
- Low-Latency Synchronization: Full-duplex WebSocket architecture broadcasting bid events instantly without page refreshes.
- Server-Authoritative Clock: Master countdown timer generated on the server to prevent local device clock tampering and sniping.
- Bid Extension Buffer: Automatic 15–20 second clock reset if a new high bid lands in the final 5–10 seconds.
- Atomic Transaction Locking: Sequential database concurrency locks to resolve simultaneous bids without race conditions.
- Anti-Spam & Rate Limiting: Cooldown buffers preventing accidental double-taps, bot spam, and artificial price pumping.
- Single Session Device Lock: Restricts team bidding access to one active concurrent device login.

---

### 5. Team & Squad Management
- Team Profiles & Purse Setup: Custom team branding, logos, assigned captains/owners, and virtual budget allocations.
- Real-Time Purse Monitor: Live financial tracking for starting balance, total spent, remaining funds, and maximum legal bid limit.
- Squad Composition Validation: Enforces minimum/maximum squad size limits and mandatory category quotas (e.g., min. 2 wicketkeepers).
- Lineup Planner: Drag-and-drop match builder to submit the Playing XI, substitutes, and captain/vice-captain designations.

---

### 6. Tournament Operations & Scheduling
- Automated Fixture Generator: Schedules round-robin, group stage, and knockout fixtures across venues and match slots.
- Schedule & Venue Management: Tools to reschedule matches, apply rain-rule adjustments, or change grounds with instant team alerts.
- Match Official Assignment: Role delegation allowing assigned scorers and umpires to manage specific match events.

---

### 7. Live Scoring, Stats & Standings
- Ball-by-Ball Live Scorer: Digital scoresheet tracking deliveries, runs, extras, dismissals, partnerships, and bowling spells.
- Auto-Calculated Standings: Real-time tournament table tracking wins, losses, points, and dynamic Net Run Rate (NRR).
- Leaderboard Automation: Real-time tracking for Orange Cap (Runs), Purple Cap (Wickets), and Tournament MVP Index.
- Shareable Match Summaries: Auto-generated digital scorecards and Player of the Match graphics.

---

### 8. Notifications & Communication
- Auction Alerts: Push/SMS updates notifying players when their category goes live or when their auction status changes.
- Match Reminders: Automated schedule reminders, reporting times, and venue directions sent to team captains.
- Live Milestone Pings: Automated real-time alerts for 50s, 100s, wickets, and match conclusions.

---

### 9. Security, Roles & Data Integrity
- Role-Based Access Control (RBAC): Distinct permissions for Super Admin, Auctioneer, Team Owner/Captain, Match Scorer, and Player/Viewer.
- Transport Layer Security: TLS/HTTPS and WSS encryption safeguarding all player data, tokens, and bid payloads.
- Tamper-Proof Audit Trail: Append-only transaction logging for every bid, score modification, and roster substitution.
