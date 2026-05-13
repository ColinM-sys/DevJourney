# Dev Journey

An interactive developer skill tracker dashboard that visualizes what I know, where I've grown, and where I'm headed next — benchmarked against real developer survey data.

Runs entirely client-side as a single HTML file. No backend, no database, no dependencies beyond Chart.js (loaded via CDN).

## Features

### Profile Card
- Estimated seniority tier (Beginner → Junior → Mid → Senior → Staff → Distinguished)
- Percentile position against the global developer distribution
- Experience-equivalent years and market salary range
- Best-fit titles (AI/ML Engineer, Full-Stack Developer, Solution Architect, etc.)
- Strengths and growth areas

### Weighted Scoring System
- **69 tracked skills** across 16 industry categories (AI/ML, Backend, Frontend, Mobile, DevOps, Cloud, Security, Testing, Systems, Architecture, Networking, Game Dev, Data Engineering, Databases, Integrations, Presentation)
- Each skill has a difficulty weight (1.0x = common, 3.0x = rare/specialized)
- Weighted score calculated as `sum(skill_level × difficulty_weight)`
- Benchmarked against SO 2024 Developer Survey, GitHub Octoverse 2024, and LinkedIn Economic Graph data

### Score Breakdown Panel
- Distribution bar showing exactly where the score lands vs. average developer
- Category contribution breakdown — see which categories drive the total
- Top 10 weighted skills ranked by contribution
- Explanation of the math

### Skill Bars
- 69 skills with animated progress bars
- Difficulty weight displayed next to each skill name
- Filterable by category (All, AI/ML, Backend, Frontend, etc.)
- Grouped by category with averages per group

### GitHub Portfolio Section
- All 16 public repos displayed as clickable cards
- Shows primary language, creation date, and description
- Links directly to GitHub repo pages

### Learning Timeline
- 30+ events chronicling progression from first Python exposure to shipping RAG-powered platforms
- Includes hackathon wins, GitHub repo creations, and major technical milestones
- 3 predicted future milestones for next 1–12 months

### Predicted Next Skills Panel
- 9 predictions with confidence percentages
- Each prediction includes reasoning based on current trajectory
- Examples: Streaming LLM responses (85%), NVIDIA NIM/Triton (75%), PostGIS (70%)

### Charts
- **Radar chart**: skill levels across 16 categories, overlaid against average developer baseline
- **Velocity chart**: cumulative skill growth + monthly new-skill counts, with dashed projections for Jun 2026, Oct 2026, and Apr 2027

## Methodology

Skill levels use a 0–100 scale where:
- 0 = never touched
- 20 = tutorial-level
- 40 = can build simple things with docs
- 60 = can build real features independently
- 80 = deep understanding, complex systems
- 100 = expert, can architect at scale

Percentile thresholds calibrated against:
- **Stack Overflow 2024 Developer Survey**: technology adoption rates, years-of-experience distribution, languages-per-dev averages
- **GitHub Octoverse 2024**: median 4 repos/user, 3–4 languages/user
- **LinkedIn Economic Graph / Burning Glass**: skill counts by seniority tier (junior 3–6, mid 6–12, senior 10–18, staff 15–25)

The percentile lookup table maps weighted scores to percentiles:
- 170 pts = 50th percentile (median developer profile)
- 450 pts = 80th percentile (senior)
- 700 pts = 95th percentile (staff)
- 1000 pts = 99th percentile (distinguished)

## Running

Just open `index.html` in any browser. No server required.

For a local dev server:
```bash
python -m http.server 8055
```

Then open http://localhost:8055

## Stack

- Single HTML file
- Vanilla JavaScript (no framework)
- Chart.js (CDN) for radar and velocity charts
- CSS custom properties for theming

## About

Personal developer skill tracker — skill data, timeline, and predictions are hand-curated for my own career trajectory. The scoring methodology is open and adaptable if you want to fork it and build your own version.
