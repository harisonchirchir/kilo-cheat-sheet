# Debugging API Issues

## Overview

This guide demonstrates how to use Kilo Code to debug API-related issues effectively.

## Common API Issues

### 1. Authentication Errors

**Symptoms:**
- 401 Unauthorized
- 403 Forbidden
- Invalid token errors

**Debugging Steps:**

```text
/debug src/auth.js --error=401
```

**Example:**
```text
/explain src/middleware/auth.js
# AI analyzes the authentication middleware
```

### 2. Validation Errors

**Symptoms:**
- 400 Bad Request
- Invalid input errors
- Missing required fields

**Debugging Steps:**

```text
/debug src/validation.js --error=400
/refactor src/validation.js --target=improve-errors
```

### 3. Database Errors

**Symptoms:**
- 500 Internal Server Error
- Connection timeouts
- Query failures

**Debugging Steps:**

```text
/debug src/database.js --error=connection
/explain src/queries/user.js --focus=performance
```

### 4. Network Issues

**Symptoms:**
- Timeout errors
- DNS failures
- Connection refused

**Debugging Steps:**

```text
/debug src/api-client.js --error=timeout
/optimize src/api-client.js --target=reliability
```

## Debugging Commands

### Analyze Error Logs

```text
/analyze logs/error.log --focus=api-errors
```

### Debug Specific Endpoint

```text
/debug src/api/users.js --endpoint=POST /users
```

### Check API Performance

```text
/performance analyze src/api/ --focus=slow-endpoints
```

### Test API Responses

```text
/test src/api/users.js --test=response-validation
```

## Debugging Workflow

### Step 1: Identify the Issue

```text
/debug --error=500 --file=api.js
```

### Step 2: Analyze the Code

```text
/explain src/api/users.js --focus=error-handling
```

### Step 3: Find Root Cause

```text
/analyze src/database.js --focus=connection-pool
```

### Step 4: Implement Fix

```text
/refactor src/database.js --target=fix-connection-issue
```

### Step 5: Verify the Fix

```text
/test src/database.js --test=connection-pool
```

## Example Debugging Session

### Issue: API endpoint returns 500 error

```text
User: /debug src/api/users.js --endpoint=POST /users --error=500

Kilo: I've analyzed the endpoint. The issue appears to be in the database query. 
Let me check the user creation logic...

User: /explain src/database/users.js

Kilo: The issue is in the `createUser` function. The email field is not being validated 
before the database insert, causing a constraint violation.

User: /refactor src/database/users.js --target=add-validation

Kilo: I've added email validation before the database insert. Here's the updated code...
```

## Best Practices

- Use descriptive error messages
- Log errors with context
- Implement proper error handling
- Use error tracking tools
- Regularly review error logs
- Set up monitoring and alerts
