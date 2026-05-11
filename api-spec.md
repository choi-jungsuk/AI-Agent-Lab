# Southeast Asia Expert AI Agent API Specification

## Overview
The Southeast Asia Expert AI Agent provides market intelligence and business consulting services for Korean companies expanding into Southeast Asia. The agent is modeled after KOTRA's Global Business Consultant (GBC).

## Authentication
All endpoints require an `X-API-Key` header.

## Request Format
All requests use POST method with JSON body:
```json
{
  "target_country": "string",
  "industry": "string",
  "company_profile": {
    "size": "S/M/L",
    "sector": "string"
  },
  "objective": "string",
  "parameters": {}
}
```

## Response Format
All responses use JSON:
```json
{
  "success": true,
  "data": {
    "analysis": "string",
    "results": {},
    "recommendations": []
  },
  "metadata": {
    "request_id": "string",
    "timestamp": "ISO8601"
  }
}
```

## Endpoints

### 1. Market Research & Analysis
**POST** `/api/v1/market-research`

Request:
```json
{
  "target_country": "Vietnam",
  "industry": "electronics",
  "company_profile": {"size": "M", "sector": "manufacturing"},
  "objective": "market_entry",
  "parameters": {"depth": "detailed"}
}
```

Response:
```json
{
  "success": true,
  "data": {
    "analysis": "Southeast Asia market analysis for electronics...",
    "results": {
      "market_size": "$XXB",
      "growth_rate": "X%",
      "key_trends": [...]
    },
    "recommendations": [...]
  }
}
```

### 2. Business Matching
**POST** `/api/v1/business-matching`

Request:
```json
{
  "target_country": "Thailand",
  "industry": "food_beverage",
  "company_profile": {"size": "L", "sector": "manufacturing"},
  "objective": "buyer_discovery",
  "parameters": {"match_type": "distributor"}
}
```

Response:
```json
{
  "success": true,
  "data": {
    "analysis": "Potential buyer profiles identified...",
    "results": {
      "matching_score": 0.85,
      "buyer_profiles": [
        {
          "name": "ABC Trading",
          "contact": "john@abc.com",
          "specialty": "food_distribution"
        }
      ]
    },
    "recommendations": [...]
  }
}
```

### 3. Market Entry Strategy
**POST** `/api/v1/market-entry`

Request:
```json
{
  "target_country": "Indonesia",
  "industry": "renewable_energy",
  "company_profile": {"size": "M", "sector": "technology"},
  "objective": "market_entry",
  "parameters": {"entry_mode": "joint_venture"}
}
```

Response:
```json
{
  "success": true,
  "data": {
    "analysis": "Market entry strategy analysis for renewable energy in Indonesia...",
    "results": {
      "regulatory_requirements": [...],
      "tariff_structure": {...},
      "certification_needed": ["ISO 9001", "Local Content Requirement"]
    },
    "recommendations": [...]
  }
}
```

### 4. Local Marketing Support
**POST** `/api/v1/marketing-support`

Request:
```json
{
  "target_country": "Philippines",
  "industry": "tourism",
  "company_profile": {"size": "S", "sector": "services"},
  "objective": "market_promotion",
  "parameters": {"budget": "medium", "channels": ["exhibition"]}
}
```

Response:
```json
{
  "success": true,
  "data": {
    "analysis": "Local marketing strategy for tourism in Philippines...",
    "results": {
      "recommended_events": ["Philippine Travel Expo"],
      "promotion_plan": "..."
    },
    "recommendations": [...]
  }
}
```

### 5. Trade Practice Support
**POST** `/api/v1/trade-practice`

Request:
```json
{
  "target_country": "Malaysia",
  "industry": "electronics",
  "company_profile": {"size": "L", "sector": "manufacturing"},
  "objective": "trade_facilitation",
  "parameters": {"payment_terms": "L/C", "logistics": "door_to_door"}
}
```

Response:
```json
{
  "success": true,
  "data": {
    "analysis": "Trade practice consultation for electronics in Malaysia...",
    "results": {
      "contract_templates": [...],
      "logistics_options": [...],
      "payment_recommendations": [...]
    },
    "recommendations": [...]
  }
}
```

## Error Responses
All error responses follow standard format:
```json
{
  "success": false,
  "error": {
    "code": "INVALID_REQUEST",
    "message": "Validation failed"
  }
}