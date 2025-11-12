# Hono Node.js Demo

A Node.js Web application demo project based on the [Hono](https://hono.dev/) framework. Hono is an ultra-fast Web framework designed for Edge runtimes, also supporting Node.js.

## Tech Stack

- **Node.js**: 25.0.0 (managed via Volta)
- **Hono**: 4.10.3
- **@hono/node-server**: 1.19.5 (Node.js server adapter)
- **TypeScript**: 5.9.3
- **TSX**: 4.7.1 (TypeScript executor)

## Project Structure

```
hono-node-demo/
├── src/
│   ├── index.ts         # Application entry point, main route configuration
│   └── router/
│       └── users.ts     # User-related routes
├── package.json         # Project dependency configuration
├── tsconfig.json        # TypeScript configuration
├── index.http           # HTTP request test file
└── README.md
```

## Features

- Basic route handling (`GET /`)
- User API routes (`/api/v1/users`)
- Modular route structure
- TypeScript support
- Direct TypeScript execution (no compilation needed)

## Quick Start

### Prerequisites

- Node.js 25.0.0 or higher
- npm or yarn

### Installation and Running

```bash
# Install dependencies
npm install

# Run project (development mode, directly run TypeScript)
npm start

# Or build and run
npm run build
node dist/index.js
```

The service will start at `http://localhost:3000`.

### API Endpoints

#### Root Path
```http
GET http://localhost:3000/
```
Response: `Hello Hono!`

#### Get All Users
```http
GET http://localhost:3000/api/v1/users
```
Response example:
```json
[
  {"id": 1, "name": "Alice"},
  {"id": 2, "name": "Bob"}
]
```

#### Get Single User
```http
GET http://localhost:3000/api/v1/users/:id
```
Response example:
```json
{
  "id": 1,
  "name": "John Doe"
}
```

## Code Description

### Main Application (`src/index.ts`)

Application entry point, configured with:
- Create Hono application instance
- Register user routes (`/`)
- Define root path handler
- Start server using `@hono/node-server`

### User Routes (`src/router/users.ts`)

Implements user-related APIs:
- `GET /api/v1/users`: Get all users list
- `GET /api/v1/users/:id`: Get single user by ID

## Development

### Run Development Server

```bash
npm start
```

Uses TSX to directly run TypeScript files with hot reload support.

### Build Project

```bash
npm run build
```

Compiles TypeScript to JavaScript.

## Testing

Can test using HTTP requests in `index.http` file, or use curl:

```bash
# Test root path
curl http://localhost:3000/

# Test get all users
curl http://localhost:3000/api/v1/users

# Test get single user
curl http://localhost:3000/api/v1/users/1
```

## References

- [Hono Official Website](https://hono.dev/)
- [Hono CLI](https://blog.yusu.ke/hono-cli/): Hono CLI for humans and AI
- [Hono Documentation](https://hono.dev/docs)
