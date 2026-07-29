---
name: botted-playlist-auditor
description: Music streaming & playlist authenticity audit skill. Analyzes Spotify and Apple Music playlists to detect artificial stream farms, botted playlist networks, geographic anomalies, and curator red flags. Protects independent artists and labels from streaming strikes and takedowns. Use when the user says "botted playlist", "fake streams", "check this playlist", "playlist audit", "stream farm detection", or "playlist red flags".
metadata:
  version: 1.0.0
---

# Botted Playlist & Streaming Authenticity Auditor

Protects independent artists, managers, and record labels by identifying artificial streaming farms, fake playlist networks, and botted curator accounts before pitching or purchasing placement.

---

## 4 Primary Botted Playlist Heuristics

### 1. The Stream-to-Follower Ratio Anomaly
- **Organic Pattern**: 1,000 playlist followers typically yield 50 to 300 monthly streams for featured tracks.
- **Red Flag**: A playlist with 500 followers generating 50,000+ streams overnight, or a playlist with 100,000 followers yielding 10 streams.

### 2. Geographic Concentration Spikes
- **Organic Pattern**: Streams distributed across major music cities matching radio airplay and tour stops.
- **Red Flag**: 80%+ of streams coming from a single small city known for cloud server centers or click farms (e.g., specific server hubs in Finland, Buffalo, or Southeast Asia) with zero local radio or social media engagement.

### 3. Track Rotation & Turnover Velocity
- **Organic Pattern**: Curators maintain consistent genre themes and rotate 5-10 new tracks per week.
- **Red Flag**: Playlists that wipe 100% of their tracks every 48 hours, or mix completely un-related genres (e.g. death metal next to ambient acoustic) solely to service paid customers.

### 4. Curator Contact & Payment Red Flags
- **Organic Pattern**: Pitching via official submission forms, email, or verified social profiles.
- **Red Flag**: Curators requesting direct PayPal/crypto payments for "guaranteed 50k streams" or using automated Telegram bots.

---

## Audit Output Report Template

When analyzing a playlist or track trajectory:

1. **Authenticity Score (0-100%)**: Overall safety rating for pitching.
2. **Detected Red Flags**: Specific anomaly list (Geography, Followers vs Streams, Rotation).
3. **Verdict & Action**:
   - `SAFE`: Pitch via official channels.
   - `CAUTION`: Monitor streams daily via Spotify for Artists.
   - `HIGH RISK`: Do NOT pitch or accept placement. Request immediate removal if added to prevent Spotify artificial streaming flags.
