# 🎮 Video Game Sales & Subscription Strategy Dashboard

## Project Overview
This project explores global video game sales, user engagement, and critic performance data for Gamers' Arena, a video game information platform launching a subscription model for its users.
Using Tableau, the dashboard delivers dynamic, multi-dimensional analysis of game popularity, genre and platform performance, and rating patterns — equipping leadership with the insights needed to curate an attractive and profitable subscription offering.

## Business Problem
**Gamers' Arena** aims to drive user growth by designing a subscription model that gives gamers limited monthly access to a curated selection of games.

The challenge:
➡️ Identify which games, genres, and platforms maximize user engagement and sales performance to inform a compelling and commercially viable subscription strategy.

## Dataset
- 9,835 unique games across 17 platforms and 12 genres
- Key fields include: `Name`, `Platform`, `Genre`, `GlobalSales`, `CriticScore`, `UserScore`, `UserCount`, `YearOfRelease`
- Company dataset covering multi-regional global sales and user engagement metrics

## Tools & Technologies
- **Tableau Desktop / Tableau Public**

## Data Preparation / Methodology
Data was clean and required no pre-processing prior to import into Tableau. All transformations, aggregations, and feature engineering were performed directly within Tableau using calculated fields and parameters.

## Dashboard Features
- **Dynamic Top N filtering** — Parameters allow users to interactively control how many top games, platforms, or genres are displayed across visuals (by global sales, ratings, or user count)
- **3-in-1 dimension switcher** — A single parameter toggles between Games, Platforms, and Genres views across relevant charts, eliminating dashboard clutter
- **Unified ratings selector** — A calculated field consolidates User Score, Critic Score, and User Count into a single switchable metric for flexible performance comparison
- **Multi-level filters** — Name, category action, genre, and platform filters enable granular drill-down across all dashboard views

## Calculated Fields & Parameters

**Calculated Fields:**
```
// Ratings — consolidates 3 rating metrics into one switchable field
CASE [Parameters].[Ratings]
WHEN 'User Score' THEN [User Score]
WHEN 'Critic Score' THEN [Critic Score]
WHEN 'User Count' THEN [User Count]
END
```
```
// 3-in-1 — enables dimension switching between Games, Platforms, and Genres
CASE [Games / Platforms / Genres]
WHEN 'Games' THEN [Name]
WHEN 'Platforms' THEN [Platform]
WHEN 'Genres' THEN [Genre]
END
```

**Parameters used:** `Games / Platforms / Genres`, `Top N Games / Platforms / Genres by Global Sales`, `Ratings`, `Top N Games by Ratings`, `Top N Games by UserCount`

## Visualizations Included
- **Treemap:** Top N Games / Platforms / Genres by Global Sales — sized and colored by sales volume
- **Treemap:** Top N Games by Ratings & Global Sales — combined rating and sales performance view
- **Heatmap:** Global Sales Distribution Across Platforms and Genres — reveals demand concentration at the intersection of platform and genre
- **Bar Chart:** Top N Games by User Count & User Rating — highlights community engagement leaders
- **Continuous Line Chart:** Global Sales Distribution Across Release Year — tracks sales trends over time

🔗 **[View Live Dashboard on Tableau Public](https://public.tableau.com/views/VideoGameSalesSubscriptionStrategyDashboard/SuscriptionModelAnalysis?:language=en-US&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link)**

## Key Insights
- **Platform scale:** → 6,046 unique games tracked, generating $6.00B in total global sales across 1.28M users
- **Top games by global sales:** → Wii Sports, Grand Theft Auto V, and Mario Kart Wii lead the chart; Call of Duty titles dominate the top 10
- **Top platforms:** → PS2, X360, PS3, Wii, and DS account for the highest global sales volumes
- **Top genres:** → Action, Sports, and Shooter are the top 3 genres by global sales, indicating strong demand for competitive and interactive gameplay
- **Critically acclaimed titles:** → Gran Turismo, GTA V, and Super Mario Galaxy titles rank highest by critic score combined with global sales
- **Community favourites:** → The Witcher 3, The Last of Us, and Skyrim lead by user count, reflecting strong long-tail engagement from open-world RPGs
- **Peak sales years:** → 2008 and 2009 were the highest-grossing release years, with the period 2005–2011 accounting for the bulk of historical sales

## Recommendations
- **Anchor the subscription catalogue with proven blockbusters** — prioritise high-sales titles like GTA V, Mario Kart Wii, and Call of Duty entries as flagship offerings to attract and retain subscribers
- **Weight the catalogue towards Action, Sports, and Shooter genres** — these drive the highest global sales and represent the broadest audience appeal for a subscription model
- **Include community-favourite RPGs as premium or long-stay titles** — games like The Witcher 3, Skyrim, and The Last of Us have deep engagement and would improve subscriber retention through extended play sessions
- **Curate a "Critically Acclaimed" tier** — featuring titles like SoulCalibur, Metroid Prime, and Super Mario Galaxy to appeal to quality-conscious gamers and differentiate the subscription from competitors
- **Prioritise PS2, PS3, X360, and Wii-era content for catalogue depth** — these platforms represent the highest concentration of sales and offer a large pool of proven titles to license or include
- **Use the 2005–2011 peak period as a content goldmine** — games from this era dominate sales charts and carry strong nostalgia value, which can be a compelling subscription selling point
- **Monitor UserCount as a retention signal** — titles with high user counts indicate sustained community engagement; these should be prioritised for inclusion to maximise time-on-platform for subscribers

## Outcome / Impact
This dashboard enables:
- ✅ Data-driven curation of a commercially attractive subscription game catalogue
- ✅ Clear identification of high-engagement titles to drive subscriber retention
- ✅ Genre and platform intelligence to guide licensing and partnership decisions
- ✅ Executive-ready visibility into global sales trends and performance benchmarks

---

## Next Steps
- Incorporate regional sales breakdowns to tailor subscription offerings by market
- Integrate time-series forecasting to predict future genre and platform demand
- Connect to a live data source to track newly released titles and real-time sales performance
