## AI Agent API Specifications

This section provides the API specifications for the AI Agent, detailing the endpoints, request formats, response formats, and authentication mechanisms.

### Base URL
```
http://172.18.0.3:5001/
```

### Endpoints Overview

| Endpoint                      | Method | Description                             |
|-------------------------------|--------|-----------------------------------------|
| `/agents`                     | GET    | List all registered AI Agents.         |
| `/agents`                     | POST   | Register a new AI Agent.               |
| `/agents/{id}`                | GET    | Retrieve details of a specific Agent.  |
| `/agents/{id}`                | PUT    | Update the configuration of an Agent.  |
| `/agents/{id}`                | DELETE | Deregister an AI Agent.                 |
| `/tasks`                      | POST   | Submit a new task for processing.      |
| `/tasks/{id}`                 | GET    | Retrieve the status of a submitted task. |
| `/monitoring/performance`     | GET    | Get performance metrics of the AI Farm. |
| `/data/ingestion`             | POST   | Ingest real-time data from sources.    |

### Request Formats

#### Headers

All requests should include the following headers:

- `Content-Type: application/json`
- `Authorization: Bearer <API_TOKEN>`

#### Example Request Body

**Registering an AI Agent**

```json
{
  "name": "ExampleAgent",
  "type": "NLP",
  "configuration": {
    "max_memory": "4GB",
    "cpu_cores": 2
  }
}
```

**Submitting a Task**

```json
{
  "agent_id": "example-agent-id",
  "task_data": {
    "input": "What is the weather like today?",
    "parameters": {
      "response_format": "text"
    }
  }
}
```

### Response Formats

#### General Response Structure

```json
{
  "status": "success", // or "error"
  "data": { // contains the response data on success
    // response specific fields
  },
  "message": "Optional error or success message."
}
```

#### Example Response for Task Status

```json
{
  "status": "success",
  "data": {
    "task_id": "task123",
    "status": "completed",
    "result": "The weather is sunny with a temperature of 75°F."
  },
  "message": "Task completed successfully."
}
```

### Authentication

**API Key Authentication**

- Each request must be accompanied by an API token in the Authorization header.
- Tokens are issued during the registration of the AI Agent and can be revoked as necessary.

