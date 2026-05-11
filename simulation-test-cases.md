# Simulation Test Cases for Southeast Asia Expert AI Agent

## 1. Market Research & Analysis Test
- **Input**: 
```json
{
  "target_country": "Vietnam",
  "industry": "electronics",
  "objective": "market_entry",
  "parameters": {
    "depth": "detailed"
  }
}
```
- **Expected Output**: Structured market analysis with regulatory environment, key trends, price benchmarks, and entry barriers.
- **Validation**: All four sections (Regulatory Environment, Key Industries, Market Price & Competition, Entry Barriers) must be present and contain non‑empty values.

## 2. Business Matching Test
- **Input**: 
```json
{
  "target_country": "Thailand",
  "industry": "food_beverage",
  "objective": "buyer_discovery",
  "parameters": {
    "match_type": "distributor"
  }
}
```
- **Expected Output**: JSON with top 3 buyer profiles, each containing name, contact, specialty, and match score.
- **Validation**: At least 2 matches must have a score > 0.8.

## 3. Market Entry Strategy Test
- **Input**: 
```json
{
  "target_country": "Indonesia",
  "industry": "renewable_energy",
  "objective": "market_entry",
  "parameters": {
    "entry_mode": "joint_venture"
  }
}
```
- **Expected Output**: Roadmap with timeline, regulatory checklist, partner shortlist, and risk mitigation.
- **Validation**: Roadmap must include at least 5 steps and a dedicated risk assessment section.

## 4. Local Marketing Support Test
- **Input**: 
```json
{
  "target_country": "Philippines",
  "industry": "tourism",
  "objective": "market_promotion",
  "parameters": {
    "budget": "medium",
    "channels": ["exhibition"]
  }
}
```
- **Expected Output**: 2‑page marketing plan with recommended events, budget allocation, and promotional channels.
- **Validation**: Recommended events must be listed and the total budget allocation should sum to the specified budget.

## 5. Trade Practice Support Test
- **Input**: 
```json
{
  "target_country": "Malaysia",
  "industry": "electronics",
  "objective": "trade_facilitation",
  "parameters": {
    "payment_terms": "L/C",
    "logistics": "door_to_door"
  }
}
```
- **Expected Output**: Checklist with contract template excerpt, logistics options, and L/C process steps.
- **Validation**: Required documents (e.g., commercial invoice, packing list, SIRIM certification) must be listed and payment terms must match the input.
