# Agentic AI Resume Agent - MuleSoft MCP Integration

A personal MuleSoft proof of concept created in 2026 to expose structured professional-profile data through both a REST API and Model Context Protocol (MCP) tools.

## Purpose

The project demonstrates how a MuleSoft application can make structured profile information available to API consumers and AI clients. It was built as a personal technical project to explore current integration patterns around MCP, API design, DataWeave transformation and cloud-ready Mule application development.

## Architecture

The application contains two access paths:

1. **REST API**
   - RAML 1.0 API specification
   - APIKit routing
   - HTTP listener
   - JSON responses
   - DataWeave transformations and filtering

2. **Native MCP Server**
   - MuleSoft MCP Connector 1.6.1
   - Streamable HTTP transport
   - MCP endpoint at `/mcp`
   - Nine MCP tools that expose profile, experience, skills, education, certifications, projects, achievements and keyword search

Both REST and MCP interfaces reuse the same underlying implementation flows and structured data source.

## Main MCP Tools

- `get-profile`
- `get-experience`
- `get-experience-by-company`
- `get-skills`
- `get-education`
- `get-certifications`
- `get-projects`
- `get-achievements`
- `search-resume`

## Technology Stack

- Mule Runtime 4
- MuleSoft MCP Connector 1.6.1
- RAML 1.0
- APIKit
- DataWeave 2.0
- HTTP Connector
- Maven
- Java 17
- Postman
- CloudHub 2.0 compatible configuration

## Project Structure

- `src/main/resources/api/resume-ai-agent-api.raml` - REST API contract
- `src/main/mule/resume-ai-agent-api-v1.xml` - REST API flows
- `src/main/mule/mcp-server.xml` - MCP tool definitions
- `src/main/mule/resume-impl.xml` - shared implementation and DataWeave logic
- `src/main/mule/global-configs.xml` - HTTP, APIKit and MCP configuration
- `src/main/resources/data/resume-data.json` - structured project data source
- `postman/` - REST and MCP Postman collections and environments
- `services/claude-desktop-config.json` - local MCP client configuration example

## Local Endpoints

REST API:

```
http://localhost:8081/api/v1/resume/*
```

MCP Server:

```
http://localhost:8081/mcp
```

## Testing

The repository includes Postman collections for:

- REST endpoint testing
- MCP initialization and session handling
- MCP tool discovery
- MCP tool invocation
- profile and experience queries
- certification and project queries
- keyword search

The MCP server configuration is also suitable for testing with MCP-compatible clients such as Claude Desktop and MCP Inspector.

## Professional Currency Context

This repository is maintained as a personal technical artefact demonstrating recent hands-on work in:

- API design
- MuleSoft application development
- DataWeave transformation
- reusable integration flows
- MCP tool design
- HTTP-based integration
- testing and troubleshooting
- cloud-ready deployment design

Created and maintained by **Dinesh Babu R** in 2026.
