## Task 1

**Task Type:** Feature Implementation

**Prompt:**
```
Add JWT Auth Middleware support for the Hono.js application with HS256 algorithm and secret `your-256-bit-secret`. Requirements:

- Add JWT verification for `/api/v1/*`, allow other URLs to pass through
- Return 401 status code and JSON format error message when verification fails
- Add functionality to obtain JWT based on username and password. The generated JWT token's payload sub should be username, with an expiration time of 30 days
- JWT token comes from the `Authorization` header field in the format `Bearer <token>`, and also supports passing JWT Token through the x-api-key query parameter
```

