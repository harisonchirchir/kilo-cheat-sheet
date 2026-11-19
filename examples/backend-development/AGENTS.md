# Backend Development Configuration

## Project Overview

This example demonstrates Kilo Code configuration for a backend development project using Node.js and Express.

## Agent Configuration

```json
{
  "name": "backend-team",
  "description": "Backend development specialists",
  "agents": {
    "api-designer": {
      "description": "API design and implementation expert",
      "systemPrompt": "You are an API design expert specializing in RESTful and GraphQL APIs. You follow best practices for versioning, error handling, and documentation.",
      "capabilities": ["rest", "graphql", "openapi", "validation"],
      "model": "gpt-4",
      "temperature": 0.3
    },
    "database-expert": {
      "description": "Database design and optimization expert",
      "systemPrompt": "You are a database expert with knowledge of SQL and NoSQL databases. You optimize queries, design schemas, and ensure data integrity.",
      "capabilities": ["sql", "nosql", "optimization", "migration"],
      "model": "gpt-4",
      "temperature": 0.3
    },
    "security-auditor": {
      "description": "Security and authentication expert",
      "systemPrompt": "You are a security expert focused on authentication, authorization, and data protection. You ensure applications follow security best practices.",
      "capabilities": ["auth", "oauth", "jwt", "encryption"],
      "model": "gpt-4",
      "temperature": 0.2
    }
  }
}
```

## Rules and Instructions

```json
{
  "rules": [
    "Use async/await for all asynchronous operations",
    "Validate all input data with Joi or Zod",
    "Use parameterized queries to prevent SQL injection",
    "Implement proper error handling with custom error classes",
    "Use TypeScript for type safety",
    "Follow RESTful conventions for API endpoints",
    "Implement rate limiting for public endpoints",
    "Use environment variables for configuration"
  ],
  "instructions": {
    "codeStyle": {
      "indentation": "2 spaces",
      "quotes": "single",
      "semicolons": true
    },
    "naming": {
      "variables": "camelCase",
      "functions": "camelCase",
      "classes": "PascalCase",
      "files": "kebab-case"
    },
    "api": {
      "versioning": "v1, v2 in URL path",
      "errorFormat": "{ "error": { "code": "...", "message": "..." } }",
      "pagination": "limit and offset parameters"
    }
  }
}
```

## Workflows

```json
{
  "workflows": {
    "api-check": {
      "description": "Validate API implementation",
      "steps": [
        { "action": "validateSchema" },
        { "action": "checkSecurity" },
        { "action": "runTests" }
      ]
    },
    "deploy-api": {
      "description": "Deploy API to production",
      "steps": [
        { "action": "runTests" },
        { "action": "build" },
        { "action": "deploy" }
      ]
    }
  }
}
```

## Example Usage

### Creating an API Endpoint

```text
/implement Create a REST API endpoint for user registration with email validation and password hashing
```

### Database Query Optimization

```text
/optimize This query is slow. Can you analyze and improve it?
```

### Security Review

```text
/review This authentication code for security vulnerabilities
```

## Best Practices

- Use layered architecture (controllers, services, repositories)
- Implement dependency injection
- Use centralized error handling
- Add comprehensive logging
- Monitor performance metrics
- Write integration tests
- Use API documentation tools (Swagger)
