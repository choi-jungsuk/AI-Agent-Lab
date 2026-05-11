# Southeast Asia Expert AI Agent – Module Scenario Designs

## 1. Market Research & Analysis
**Goal**: Provide a concise market overview for a given country and industry.

**Typical Input**
```json
{
  "target_country": "Vietnam",
  "industry": "electronics",
  "objective": "market_entry",
  "parameters": {"depth": "detailed"}
}
```
**Scenario Steps**
1. Retrieve latest regulatory data, tariff tables, and certification requirements from the research files.
2. Summarize key industry trends, growth rates, and consumer purchasing patterns.
3. Compile competitive landscape – top 3 local competitors and their market share.
4. Generate a price benchmark table for comparable products.
5. Output a structured analysis with **Regulatory Environment**, **Key Industries**, **Market Price & Competition**, and **Entry Barriers** sections.

**Sample Output**
```text
--- Market Research – Vietnam – Electronics ---
Regulatory Environment: ...
Key Industries: ...
Market Price & Competition: ...
Entry Barriers: ...
--- End of Report ---
```

---
## 2. Business Matching
**Goal**: Identify suitable local buyers or distributors for a Korean SME.

**Typical Input**
```json
{
  "target_country": "Thailand",
  "industry": "food_beverage",
  "objective": "buyer_discovery",
  "parameters": {"match_type": "distributor"}
}
```
**Scenario Steps**
1. Filter the country‑specific research for **Buyer Requirements** and **Logistics**.
2. Query a (simulated) partner database for companies meeting:
   - Distribution network size
   - ISO/halal certifications where applicable
   - Minimum order volume
3. Score each candidate on **Fit**, **Reliability**, and **Cultural Compatibility**.
4. Return top 3 matches with contact info and a brief recommendation.

**Sample Output**
```json
{
  "matches": [
    {"name":"ThaiFood Distributors Ltd","score":0.92,"contact":"info@thaifood.co.th"},
    {"name":"Bangkok Gourmet","score":0.88,"contact":"sales@bangkokgourmet.com"}
  ]
}
```
---
## 3. Market Entry Strategy
**Goal**: Produce a step‑by‑step roadmap for entering a specific market.

**Typical Input**
```json
{
  "target_country": "Indonesia",
  "industry": "renewable_energy",
  "objective": "market_entry",
  "parameters": {"entry_mode": "joint_venture"}
}
```
**Scenario Steps**
1. Extract **Regulatory Requirements**, **Tariff Structure**, and **Certification** from research.
2. Identify common **Entry Barriers** (local content, partner requirements).
3. Propose entry mode options (JV, wholly‑owned subsidiary, licensing) with pros/cons.
4. Outline a timeline:
   - Legal entity registration
   - Certification acquisition
   - Partner scouting
   - Pilot project launch
5. Provide risk assessment and mitigation suggestions.

**Sample Output**
```text
Roadmap – Indonesia – Renewable Energy (Joint Venture)
1. Register a PT PMA (foreign investment company) – 4‑6 weeks.
2. Obtain SNI certification for solar inverters – 2 months.
3. Identify local JV partner with >30% market share – shortlist 5 firms.
4. Negotiate JV agreement – 1‑2 months.
5. Pilot installation in Bali – Q3 2024.
Risks: … Mitigations: …
```
---
## 4. Local Marketing Support
**Goal**: Advise on promotional activities and channel selection.

**Typical Input**
```json
{
  "target_country": "Philippines",
  "industry": "tourism",
  "objective": "market_promotion",
  "parameters": {"budget": "medium", "channels": ["exhibition"]}
}
```
**Scenario Steps**
1. Pull **Consumer Trends** and **Preferred Channels** from research.
2. Recommend relevant trade shows, tourism expos, and digital platforms.
3. Suggest sample‑testing logistics and local PR agencies.
4. Provide a budget allocation table (exhibition, digital ads, influencer).
5. Deliver a concise 2‑page marketing plan.

**Sample Output**
```text
Marketing Plan – Philippines – Tourism
Exhibitions: Philippine Travel Expo (Oct 2024) – booth cost $5k.
Digital: Facebook & Instagram – $3k.
Influencers: 3 local travel vloggers – $2k.
Total: $10k (medium budget).
```
---
## 5. Trade Practice Support
**Goal**: Guide on contracts, logistics, and payment methods.

**Typical Input**
```json
{
  "target_country": "Malaysia",
  "industry": "electronics",
  "objective": "trade_facilitation",
  "parameters": {"payment_terms": "L/C", "logistics": "door_to_door"}
}
```
**Scenario Steps**
1. Summarize **Customs Documentation**, **Incoterms**, and **Local Payment Practices**.
2. Provide a template contract with clauses for warranty, IP protection, and dispute resolution.
3. List recommended freight forwarders and typical transit times.
4. Advise on L/C opening process, required bank documents, and risk mitigation.
5. Output a checklist and sample excerpts.

**Sample Output**
```text
Trade Checklist – Malaysia – Electronics
- Contract template attached (see Appendix A).
- Preferred freight forwarder: DHL Global Forwarding – 5‑7 days door‑to‑door.
- L/C: 30% at sight, 70% upon presentation of B/L.
- Required documents: Commercial invoice, packing list, certificate of origin, SIRIM certification.
```
---

These scenario designs will be used to generate test cases and to flesh out the API documentation later.
