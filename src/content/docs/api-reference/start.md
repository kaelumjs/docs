---
title: "start()"
description: Start the Kaelum HTTP server.
sidebar:
  order: 1
---

## Signature

```js
app.start([port], [callback])
```

## Parameters

| Name | Type | Description |
|---|---|---|
| `port` | `number` | Optional. Port to listen on. |
| `callback` | `Function` | Optional. Called when the server starts. |

**Returns:** `http.Server` instance.

## Port Precedence

1. **Explicit argument:** `app.start(5000)`
2. **Config:** `app.setConfig({ port: 4000 })`
3. **Default:** `3000`

## Examples

```js
// Default port
app.start();

// Explicit port with callback
app.start(8080, () => console.log("Running on 8080"));

// Environment variable
app.start(process.env.PORT || 3000);
```

:::note
The `start` function attaches an error listener for common errors like `EADDRINUSE`.
:::
