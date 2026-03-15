# Changelog

All notable changes to the Ants & Uncles Launcher will be documented here.

---

## [2.0.0] — 2026-03-14

### 🚀 Major Release

#### Live Score Extraction Rewrite
- Completely rewritten score extraction engine using IP-based memory scanning
- Accurate per-player scores with color labels (Green, Red, Blue, Black) and team ID support
- SEH-safe scanning with address caching for near-instant re-reads (~0ms vs ~300ms)
- Dynamic game timer with tick rate compensation

#### Discord Server Integration
- Revamped Discord server with organized categories and channels
- New welcome DM sent to all new members with download links and server guide
- Simplified role system — one-click "Ants Players" role for game notifications
- Step-by-step how-to-play guide posted in the Discord with images

#### Database Migration
- Migrated from Supabase to self-hosted MariaDB for lower latency and full control
- User profiles now auto-created on first login
- Moderation audit trail with persistent logging

#### Server & Backend
- Added public `/health` endpoint with rate limiting for uptime monitoring
- All information channels locked to moderator-only posting
- Server restructured with proper category organization

---

## [1.11.6] — 2026-03-14

### 🐛 Bug Fixes

- **Latency Indicators** — Fixed per-peer latency always showing empty/zero in pre-game lobbies
- **Title Bar Double-Click** — Fixed maximize/restore only working on the logo area; now works anywhere on the title bar
- **Chat Window Corners** — Fixed rounded corners not being removed when the pre-game chat is maximized
- **DevTools Leak** — Fixed developer tools opening in packaged release builds

### ✨ Improvements

- **Global Chat Scroll Lock** — New messages no longer force-scroll you to the bottom when reading older chat; a floating "↓ New Messages" button appears to jump back to live

---

## [1.11.5] — 2026-03-14

### ✨ What's New

- **User Profiles** — Your player profile is now automatically created the first time you log in, tracking username, avatar, and role

### 🐛 Fixes

- **Title Bar Drag + Double-Click** — Fixed a bug where the title bar couldn't be both dragged and double-clicked to maximize
- **Window Resize Performance** — Removed custom JavaScript resize handles that caused rubberbanding and lag; now uses native OS resize

### ✨ Improvements

- **Full Title Bar Drag Area** — The entire title bar (logo, title text, spacer) is now draggable
- **Visual Refinements** — Default cursor on drag areas, native OS window corners matching Win11

---

## [1.11.4] — 2026-03-14

### 🐛 Bug Fixes

- **Exit Dialog Persistence** — Fixed "Don't ask again" preference not being saved across polling cycles
- **Token Redaction** — Sensitive tokens no longer appear in client logs

---

## [1.11.0 – 1.11.3] — 2026-03-06

### ✨ Improvements

- **Exit Preferences** — New exit behavior settings with minimize-to-tray and "don't ask again" options
- **DevTools Suppression** — Fixed DevTools opening on Windows auto-start

---

## [1.9.0 – 1.9.3] — 2026-02-14 – 2026-02-20

### 🐛 Bug Fixes

- **Discord Auth** — Fixed login flow hanging due to redirect URI mismatch (`:443` normalization)
- **Token Redaction** — Sensitive auth tokens no longer leak to client logs

### ✨ Improvements

- **Auth Error Handling** — UI now shows clear error messages instead of hanging on failed Discord login
- **Server-Side Retries** — OAuth token exchange now retries on transient Discord API failures

---

## [1.8.0] — 2026-02-13

### ✨ Improvements

- **Admin Status Persistence** — Admin/Moderator status now persists across sessions with server-side verification
- **Security Hardening** — P2P and admin API endpoints hardened against unauthorized access

---

## [1.7.0] — 2026-02-13

### ✨ Improvements

- **Security** — Hardened admin and P2P security with server-side permission checks
- **Settings Panel** — Refined settings panel layout and behavior
- **Discord Identity** — Improved login flow and identity mapping

### 🐛 Bug Fixes

- **Preference Crash** — Fixed crash when updating preferences in certain conditions

---

## [1.6.0] — 2026-02-13

### ✨ What's New

- **JWT Session Management** — Centralized 401 interceptor handles expired tokens automatically
- **Game Lobby Controls** — Fixed non-functional minimize/maximize buttons in the pre-game lobby

---

## [1.3.41] — 2026-01-03

### ✨ What's New

- **Live Score Sync** — Real-time score data from Ants.exe displayed in the launcher during games
- **Match History** — View past game results and scores through the public API
- **Score Thumbnails** — Lobby list shows live score previews for in-progress games
- **Team Score Aggregation** — Team scores calculated and displayed for team games
- **DND Status** — Dynamic Do Not Disturb icon with refined chat UI

### 🐛 Bug Fixes

- **Multi-Instance Stats** — Fixed score tracking when multiple game instances run
- **Color Grid** — Fixed color selection regression in lobby
- **Lobby Reset** — Server now properly resets lobbies on game over
- **Chat Deduplication** — Fixed duplicate messages appearing in global chat

---

*For more details, visit the [releases page](https://github.com/dchadd427/Ants-Launcher-Dist/releases).*
