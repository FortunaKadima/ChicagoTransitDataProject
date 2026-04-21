# Chicago Transit Data Project — Problem Statement & Value Proposition

## Problem Statement

### Current State
Chicago's CTA operates one of the largest transit networks in North America, with:
- 145+ bus routes and 8 L (train) lines
- 2,100+ bus stops and 140+ L stations
- 500M+ annual rides

**But the data is fragmented and inaccessible:**

1. **No integrated spatial analysis** — Stop locations exist but are disconnected from:
   - Surrounding urban infrastructure (roads, amenities)
   - Service coverage gaps in underserved neighborhoods
   - Accessibility metrics (walking distance to shops, hospitals, schools)

2. **No real-time operational visibility** — Transit authority has API access but it's:
   - Difficult for researchers/planners to consume
   - Not integrated with historical trends
   - Siloed from static network data

3. **Data accessibility barrier** — Raw GTFS data exists but requires:
   - Custom ETL pipelines to make it useful
   - Domain expertise to extract insights
   - Manual joins with external spatial data

4. **Limited decision-making tools** — City planners and the public lack:
   - Unified view of network quality and coverage
   - Data-driven insights for route optimization
   - Real-time service quality monitoring

---

## Why This Project Is Needed

### Stakeholders & Use Cases

**1. City of Chicago (Planning & Equity)**
- Identify underserved neighborhoods missing transit access
- Allocate resources to improve coverage in transit deserts
- Meet equity mandates: ensure low-income neighborhoods have accessible transit

**2. CTA Operations & Management**
- Real-time delay detection and root cause analysis
- Capacity planning based on demand patterns
- Service quality monitoring for accountability

**3. Commuters & Researchers**
- Interactive dashboard to explore routes and stop information
- Understand which stops have amenities, accessibility features
- Plan trips with confidence (estimated arrival, crowd levels)

**4. Urban Planners & Developers**
- Data-driven decisions on where to locate affordable housing
- Evaluate walkability and transit-oriented development (TOD) opportunities

---

## How We're Different From Competitors

### vs. Google Maps & Apple Maps
| Aspect | Google Maps | Chicago Transit Project |
|--------|------------|----------------------|
| **Real-time delays** | Limited (traffic-based) | CTA native API (actual arrival times) |
| **Spatial enrichment** | Basic (search nearby) | Deep: amenity counts, road coverage %, accessibility |
| **Historical analysis** | None | Full historical trends (busiest times, patterns) |
| **Open data** | Proprietary | 100% open source + public data |
| **Offline use** | No | Yes (local parquet files) |
| **Customization** | None | Full code + data access |

### vs. Transit Authority Websites
| Aspect | CTA.gov | Chicago Transit Project |
|--------|---------|----------------------|
| **Trip planning** | ✓ | ✓ |
| **Real-time arrival** | ✓ | ✓ |
| **Service coverage analysis** | ✗ | ✓ (road coverage %, POI access) |
| **Neighborhood equity metrics** | ✗ | ✓ (amenity distribution) |
| **Data download** | Limited | Full access (parquet + SQL) |
| **Research-friendly** | ✗ | ✓ (Snowflake + Python) |

### vs. Academic Transit Research Tools
| Aspect | Academic Tools | Chicago Transit Project |
|--------|---|---|
| **Ease of setup** | High barrier (custom code) | Docker + 1 script |
| **Real-time data** | Rare | Native support |
| **Full pipeline visible** | No (black box) | Yes (100% open) |
| **Community contributions** | No | GitHub + PRs |
| **Updated regularly** | No (one-off research) | Continuous (production pipeline) |

---

## Technical Advantages

### 1. **Comprehensive Data Integration**
- GTFS static (stops, routes, schedules)
- GTFS Realtime (live arrivals, delays)
- OpenStreetMap (roads, amenities, points of interest)
- All unified in Snowflake for fast analytics

### 2. **Spatial Analysis at Scale**
- 11,000+ stops × 16,000 amenities → analyzed with Haversine distance
- Road coverage metrics: 92.5% of primary roads within 200m of a stop
- POI access analysis: median 57 amenities within 400m of a stop

### 3. **Realtime + Historical**
- Streaming pipeline: CTA API → Kafka → Flink → Snowflake (5-min windows)
- Historical analysis: 2+ years of GTFS data in clean/analytics layers
- Trend detection: identify recurring delays, capacity issues

### 4. **Reproducible & Transparent**
- Every transformation documented and testable (44 pytest tests)
- Airflow DAG orchestrates entire pipeline
- No proprietary black boxes — all code public

---

## Business Value

### For City of Chicago
- **Cost savings**: Data-driven route optimization could reduce operational costs 5-10%
- **Equity impact**: Identify underserved areas, target service improvements
- **Public transparency**: Dashboard shows real performance metrics

### For CTA
- **Operational efficiency**: Real-time delay monitoring + root cause analysis
- **Service quality**: Historical trends identify chronic problem areas
- **Accountability**: Transparent metrics for public reporting

### For Researchers & Developers
- **Zero friction access**: Download data in Parquet, query in Snowflake SQL, or use Python
- **Living dataset**: Updated continuously as new data arrives
- **Reproducible research**: Full pipeline code available for validation

---

## Success Metrics

1. **Coverage**: 100% of CTA network (145 bus routes + 8 L lines)
2. **Freshness**: Real-time data streaming (5-min window)
3. **Accuracy**: 44 tests passing, Haversine calculations verified against known coords
4. **Accessibility**: One-click dashboard + SQL/Python for technical users
5. **Adoption**: Public repository, contributions from transit researchers

---

## Next Steps

1. **Present dashboard** to CTA management + City Planning
2. **Gather feedback** on missing analyses or data
3. **Expand**: Add bus crowding sensors (if available), fare data, accessibility features
4. **Productionize**: CloudRun or K8s for always-on pipeline
5. **Community**: Market to transit researchers, city planners, civic tech orgs
