---
name: newsjack
description: Reactive PR and Newsjacking skill powered by newsjack.cc. Scores breaking stories (tech, music industry, platform updates, AI announcements) across 4 signals (Relevance, Urgency, Viral Potential, First-Mover Advantage) and generates reactive commentary and story bridges within 30 minutes. Use when the user says "newsjack", "newsjacking", "breaking news post", "reactive PR", "score this story", or "post about this breaking news".
metadata:
  version: 1.0.0
---

# NewsJack — Reactive PR & Story Scoring Skill

Powered by the **NewsJack** framework (`newsjack.cc`). Evaluates breaking stories, industry shifts, and trending news in under 60 seconds, determining whether to post and crafting the optimal reactive angle.

---

## The 4-Signal Scoring Framework

Evaluate any breaking story on a 0-100 scale:

$$\text{Final Score} = (0.35 \times \text{Relevance}) + (0.25 \times \text{Urgency}) + (0.25 \times \text{Viral Potential}) + (0.15 \times \text{First Mover})$$

- **Score > 60**: High signal. Drop everything and post within 30 minutes.
- **Score 40 - 60**: Medium signal. Schedule a considered take today.
- **Score < 40**: Low signal. Ignore (noise).

---

## The 4 Signals Explained

### 1. Relevance (35%)
Does this sit inside your audience's core interest graph? (Genre, tools, platform policies, regulatory shifts).
- *Quick Test*: Would your reader open this story without your commentary? If yes, find a unique bridge angle. If no, you are the bridge.

### 2. Urgency (25%)
- **Critical (0-2h)**: Breaking platform changes, major label exits, viral controversies.
- **High (2-24h)**: Industry reports, product launches, tool updates.
- **Medium (2-7 days)**: Feature trends, market analysis.

### 3. Viral Potential (25%)
Does the story have concrete numbers, a counter-intuitive finding, or a 1-line shareable takeaway?

### 4. First-Mover Advantage (15%)
Are other accounts already covering it? If top search results on X are > 4 hours old, the first-mover window is closing.

---

## Reactive Post Output Templates

When a story scores > 60, produce 3 reactive post options:

1. **The Bridge Angle**: Connects the breaking story directly to your product thesis or audience pain point.
2. **The Counter-Narrative**: Challenges the popular takeaway with a practitioner's perspective.
3. **The Data-First Takearound**: Highlights the specific numbers or policy clause others missed.
