# Chicago Transit Data Project - 3 Slide Pitch (3 minutes)

**Prompt for ChatGPT:** "Create a professional 3-slide presentation deck based on this brief. Make it visually striking and present-able in 3 minutes (1 minute per slide). Format for Google Slides/PowerPoint."

---

## SLIDE 1: THE PROBLEM (1 minute)

**Title:** Fragmented Transit Data

**Key points:**
- Chicago CTA: 145 bus routes, 8 L lines, 500M+ annual riders
- Data exists but is scattered across 3 sources: GTFS schedules, realtime API, OpenStreetMap
- **Nobody can answer:** Where are service gaps? Which stops lack amenities? Why are certain routes always late?
- Result: City planners can't optimize equity, CTA can't identify operational issues, public can't access comprehensive data

**Speaker notes:** "Every day, 500 million people ride Chicago transit. But the data that could improve service is invisible, fragmented, and inaccessible. We fixed that."

**Visual suggestion:**
- Left side: 3 overlapping circles labeled "GTFS Schedule Data," "GTFS Realtime API," "OpenStreetMap"
- Right side: Large red "?" or "fragmented" icon
- Big statement: "Nobody is connecting these dots"

**Color:** Bold reds/oranges to emphasize the problem

---

## SLIDE 2: OUR SOLUTION (1 minute)

**Title:** Unified Real-Time Analytics Platform

**What we built:**
1. **Integrated** all 3 data sources into one platform
2. **Analyzed** 11k stops × 16k amenities to show service coverage (92.5% of roads covered)
3. **Built streaming pipeline** — realtime vehicle positions + delays updated every 30 seconds
4. **Created interactive dashboard** — 6 views (busiest stops, routes, POI access, coverage, realtime)

**Key metric:** <5 minute latency from CTA API to live dashboard

**Speaker notes:** "We built a production pipeline. GTFS + Realtime + OSM all go into Snowflake. We analyze it with Spark. We stream realtime updates with Kafka and Flink. And we display it in a dashboard anyone can use—no technical skills required."

**Visual suggestion:**
- Center: Flow diagram (left to right)
  - Input icons: GTFS, Realtime API, OSM
  - Arrow to middle: "PySpark + Snowflake + Flink"
  - Arrow to right: Streamlit dashboard icon
- Bottom: "Live realtime | Historical data | Spatial analysis | Open source"

**Color:** Blue (CTA colors) with green checkmarks

---

## SLIDE 3: IMPACT & CALL TO ACTION (1 minute)

**Title:** Real-World Impact

**Who benefits:**
- **City planners** — "South side has service gaps—add 3 routes here"
- **CTA operations** — "Route 82 has 15% delay ratio—investigate"
- **Commuters** — "Find stops near schools and jobs within walking distance"
- **Developers & researchers** — Open source repo, download full dataset

**Data by the numbers:**
- 10 GitHub issues resolved
- 44 automated tests (100% passing)
- 15 Snowflake tables (RAW → CLEAN → ANALYTICS)
- 500k+ events/day flowing through pipeline

**Call to action:**
- **GitHub:** [repo link]
- **Dashboard:** localhost:8501 (or deployed URL)
- **Feedback:** We're looking for early adopters from CTA, City Planning, and transit tech community

**Speaker notes:** "This isn't just a dashboard. It's a reproducible, open-source platform that any city can adapt. We're inviting CTA to use it for operations, the city to use it for planning, and developers everywhere to fork it and improve it."

**Visual suggestion:**
- Left: 4 icons representing stakeholders (planner, bus driver, commuter, developer)
- Center: Large dashboard screenshot (showing live realtime view)
- Right: Upward arrow (growth/impact)
- Bottom: GitHub logo + "Open source, transparent, reproducible"

**Color:** Bright, optimistic (greens, blues)

---

## TIMING BREAKDOWN

| Slide | Topic | Duration | Speaker |
|-------|-------|----------|---------|
| 1 | Problem: Fragmented data | 1 min | [Name] |
| 2 | Solution: Unified platform | 1 min | [Name] |
| 3 | Impact & call to action | 1 min | [Name] |
| — | Q&A | 2-3 min | [Names] |
| **Total** | **Presentation** | **3 min** | |

---

## TALKING POINTS - WORD FOR WORD

**Slide 1 opening (30 sec):**
"Every day, half a billion people move through Chicago on transit. But the data that could improve their experience—where they go, when they go, why they go—that data is scattered across three separate sources and nobody's connecting the dots. As a result, city planners can't identify service gaps. CTA can't spot operational problems. And the public can't access comprehensive information about their transit network."

**Slide 2 (30 sec):**
"So we built a unified platform. We pulled all three data sources—GTFS schedules, the CTA's realtime API, and OpenStreetMap—and integrated them in Snowflake. We used Spark to clean and analyze the data. We use Kafka and Flink to stream realtime updates every 30 seconds. And we created a dashboard that makes all this visible to everyone: city planners, transit operators, researchers, and commuters. The data shows us that 92.5% of Chicago's primary roads have transit within 200 meters. It shows which stops have the best amenity access. And it shows, in real time, where delays are happening."

**Slide 3 (30 sec):**
"The impact: City planners can now see exactly where service gaps exist and make data-driven decisions about where to add routes. CTA operations can spot chronic delays and investigate. Commuters can explore their neighborhood's transit connectivity. And developers everywhere can fork our open-source repo and build the same platform for their city. We've delivered 10 features, 44 automated tests, a production pipeline, and a live dashboard. And we're inviting early adopters—from CTA, from City Planning, from the transit tech community—to use it, test it, and help us improve it."

---

## DESIGN TIPS

**Font:** Bold, clean, readable from back of room
- Titles: 44-48pt
- Bullets: 28-32pt
- Never more than 4 bullets per slide

**Layout:** Minimal text, maximum visuals
- Slide 1: Problem on left, fragmentation icon on right
- Slide 2: Data flow across the center, live screenshot below
- Slide 3: Stakeholders on left, dashboard in center, impact arrow on right

**Color palette:**
- CTA Blue (#003DA5) as primary
- Chicago Red (#C6192B) for accents
- White/light gray backgrounds
- Green (#00A651) for success/checkmarks

**Visuals:**
- Real dashboard screenshots (makes it concrete)
- Simple icons (not complex diagrams)
- One map showing coverage heatmap
- GitHub/code snippets optional (show that it's real)

**Practice delivery:**
- 20 sec on problem (why this matters)
- 20 sec on solution (what we built)
- 20 sec on impact (who benefits + call to action)
