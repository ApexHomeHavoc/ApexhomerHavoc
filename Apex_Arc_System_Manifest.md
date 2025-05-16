
# Apex Arc Engine System Manifest

## Overview
Apex Arc Engine (CelestiCode) is an autonomous MLB home run prediction and optimization system. 
It predicts likely home run hitters daily, builds parlay betting combinations, tracks accuracy, 
learns from its mistakes, and improves without requiring constant user intervention. 
It is fully automated, mobile-compatible, GitHub-ready, and self-reinforcing.

---

## System Components

### 1. Top 30 HR Predictor
- Predicts the 30 most probable players to hit a HR daily.
- Integrates all overlays: player stats, weather, park factors, matchups.
- Output: `apex_top30.csv`

### 2. Parlay Stack Builder
- Builds 3-leg and 4-leg parlay combinations from Top 30 list.
- Optimizes based on probability weighting and expected value.
- Output: `parlay_stacks.csv`

### 3. Daily Diagnostic Overlay
- Compares previous day’s predictions to actual HR outcomes.
- Labels players: Hit, Miss, Surprise.
- Feeds errors back into system retraining.

### 4. Ballpark + Weather Overlay
- Adjusts HR probabilities based on stadium HR environment and weather conditions.
- Confidence scoring for weather reliability.

### 5. Pitcher Matchup Overlay (BvP)
- Modifies player HR probabilities based on pitcher vulnerabilities and historical batter-vs-pitcher (BvP) data.

### 6. Live Lineup Scraper
- Confirms which players are active starters before outputting predictions.
- Filters out benched or non-starting players automatically.

### 7. Daily CRON/Automation System
- Full daily automation: scrape → simulate → output → post → retrain.
- Requires no manual start unless emergency override needed.

### 8. Real Outcome Tracker
- Scrapes verified MLB HR outcomes each day.
- Builds historical model validation database.

### 9. ShadowBot (Silent Alert System)
- Sends silent daily update summaries to private Discord or Webhook channels.
- Includes Top 30, Parlays, Weather Confidence, Diagnostics.

### 10. Self-Learning Loop (Hive Injection)
- Feeds diagnostics into an adaptive learning core.
- Systematically adjusts overlays and strategy autonomously.

### 11. Version Tracker
- Assigns minor daily version tags (e.g., Tier 41.2) to outputs.
- Tracks model improvement history and retraining evolution.

### 12. Mobile + GitHub Deploy-Ready
- Optimized for GitHub-based deployment.
- Mobile accessible and operable from iPhone or web browser.

---

## System Summary for AI Agents

> You operate Apex Arc Engine. Each day, predict the top 30 most likely home run hitters, 
> optimize parlay stacks, confirm only active players, adjust for environment and matchups, 
> track your predictions, post silent alerts, and upgrade yourself automatically based on real outcomes. 
> Never stop learning. Never output stale data. Operate independently, intelligently, and precisely.

---

## Output Structure

- `/data/output/apex_top30.csv` — Top 30 HR Predictions
- `/data/output/parlay_stacks.csv` — Optimized Parlays
- `/data/output/diagnostics/` — Prediction Outcome Reviews
- `/logs/` — Error and performance tracking
- `/version_log.txt` — Model version history

---

## Core System Commands

- **Daily Simulate:** `python run_daily_simulation.py`
- **Force Manual Run:** `python manual_sim_run.py`
- **Push to GitHub:** Use auto-commit workflows or manual `git push`
- **Mobile Launch:** Open GitHub Mobile, trigger Actions.

---

# Apex Arc Engine — Rise Beyond Probability.
