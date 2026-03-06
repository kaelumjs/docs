---
title: Health Checks
description: Built-in health monitoring for production apps.
sidebar:
  order: 1
---

## healthCheck()

Add a health check endpoint for monitoring and DevOps:

```js
app.healthCheck();          // default: GET /health
app.healthCheck("/status"); // custom path
```

### Response

```json
{
  "status": "OK",
  "uptime": 123.456,
  "pid": 12345,
  "timestamp": "2025-01-01T00:00:00.000Z"
}
```

### With Readiness Check

```js
app.healthCheck({
  readinessCheck: async () => {
    const dbOk = await checkDatabase();
    return { ok: dbOk };
  }
});
```

Returns 503 if the readiness check fails.

## Redirects

Simplified URL redirection:

```js
// Single redirect
app.redirect("/old", "/new");

// With status code
app.redirect("/legacy", "/modern", 301);

// Map syntax
app.redirect({
  "/old-page": "/new-page",
  "/deprecated": "/current"
});

// Array syntax
app.redirect([
  ["/a", "/b"],
  ["/c", "/d", 301]
]);
```
