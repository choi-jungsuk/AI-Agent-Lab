# Integration Guidelines for k-statra.com Backend Developers

## 1. Overview
The Southeast Asia Expert AI Agent is designed as a standalone API server that k-statra.com can integrate with via RESTful API calls. This document provides guidelines for backend developers to connect the existing platform with the agent.

## 2. API Base URL
- **Development**: `http://localhost:8000/api/v1`
- **Production**: `https://sea-expert-api.k-statra.com/api/v1` (to be confirmed)

## 3. Authentication
All API requests must include the `X-API-Key` header:
```
X-API-Key: <your_unique_api_key>
```
Contact the system administrator to obtain an API key.

## 4. Integration Steps

### Step 1: API Client Setup
Create an HTTP client in your backend (e.g., Axios for Node.js, RestTemplate for Java) with the base URL and authentication header.

### Step 2: Map k-statra.com Data to Agent Request Schema
Ensure your platform's data (company profile, target country, industry) matches the agent's request format:
```json
{
  "target_country": "string",  // e.g., "Vietnam", "Thailand"
  "industry": "string",        // e.g., "electronics", "food_beverage"
  "company_profile": {
    "size": "S/M/L",           // Small/Medium/Large
    "sector": "string"          // e.g., "manufacturing", "services"
  },
  "objective": "string",       // e.g., "market_entry", "buyer_discovery"
  "parameters": {}             // Module-specific parameters
}
```

### Step 3: Endpoint Integration
Integrate each of the 5 agent modules with corresponding k-statra.com features:

| Agent Module          | k-statra.com Feature to Integrate       | Endpoint Path                  |
|-----------------------|------------------------------------------|--------------------------------|
| Market Research       | Market analysis dashboard                | `/api/v1/market-research`      |
| Business Matching     | Buyer discovery page                     | `/api/v1/business-matching`    |
| Market Entry Strategy | Market entry roadmap generator           | `/api/v1/market-entry`         |
| Local Marketing       | Marketing plan creator                   | `/api/v1/marketing-support`    |
| Trade Practice        | Trade documentation assistant             | `/api/v1/trade-practice`       |

### Step 4: Response Handling
Parse the agent's JSON response and map it to your platform's UI components. Example response structure:
```json
{
  "success": true,
  "data": {
    "analysis": "string",       // Main analysis text
    "results": {},              // Structured data (e.g., buyer list, roadmap steps)
    "recommendations": []       // Actionable recommendations
  },
  "metadata": {
    "request_id": "string",     // For debugging
    "timestamp": "ISO8601"      // Response time
  }
}
```

### Step 5: Error Handling
Implement error handling for common HTTP status codes:
- `400 Bad Request`: Invalid request parameters (validate input before sending)
- `401 Unauthorized`: Invalid/missing API key
- `404 Not Found`: Invalid endpoint path
- `500 Internal Server Error`: Agent server error (implement retry logic with exponential backoff)

## 5. Example Integration Code (Node.js/Axios)
```javascript
const axios = require('axios');

const apiClient = axios.create({
  baseURL: 'http://localhost:8000/api/v1',
  headers: { 'X-API-Key': process.env.SEA_AGENT_API_KEY }
});

async function getMarketResearch(country, industry) {
  try {
    const response = await apiClient.post('/market-research', {
      target_country: country,
      industry: industry,
      company_profile: { size: 'M', sector: 'manufacturing' },
      objective: 'market_entry',
      parameters: { depth: 'detailed' }
    });
    return response.data;
  } catch (error) {
    console.error('Agent API error:', error.response?.data || error.message);
    throw error;
  }
}
```

## 6. Testing
Use the simulation test cases provided in `simulation-test-cases.md` to validate your integration. Ensure each module returns the expected data structure.

## 7. Deployment Notes
- The agent API server should be deployed in a secure environment with SSL/TLS.
- Monitor API usage and response times using the `request_id` in metadata for tracing.
- Rate limiting: Maximum 100 requests per minute per API key (to be adjusted based on usage).

## 8. Support
For questions or issues, contact the AI Agent development team at `ai-agent-support@k-statra.com`.
