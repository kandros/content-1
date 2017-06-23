---
alias: eip7ahqu5o
path: /docs/reference/auth/authentication-tokens
layout: REFERENCE
description: Authentication allows you to manage users in your GraphQL backend. Use authentication providers like Auth0 and Digits out-of-the-box.
tags:
  - authentication
related:
  further:
  more:
---

# Authentication Tokens

Requests to your [API](!alias-heshoov3ai) are authenticated using **authentication tokens** that are typically [JWT (JSON Web Tokens)](https://jwt.io/).

## Authenticating a Request

Authentication tokens need to be passed using the `Authorization` HTTP header:

```plain
Authorization: Bearer <authentication token>
```

If a request to your endpoint contains a valid authentication token, it is considered authenticated with regards to the [permission system](!alias-iegoo0heez). A request with an invalid authentication token in its header is treated as if the token would not be passed at all.

## Token Types

**Temporary authentication** tokens are associated with a specific node of the [`User` type](!alias-uhieg2shio#user-type) and have a certain validity duration. They can be issued from one of the active [authentication providers](!alias-seimeish6e#authentication-providers) in your project.

**Permanent authentication tokens (PATs)** are useful for server-side scripts that need access to your data. You can manage them in your [project settings](!alias-aechi6iequ).

![](./copy-pat.gif?width=400)

> Be **very** careful where you use the permanent authentication tokens. Everyone with a permanent authentication token has full read and write access to your data, so you should never include them anywhere client-side, like on a public website or a mobile app.
