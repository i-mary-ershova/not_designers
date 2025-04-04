# Hackathon Project Setup

This repository contains two main projects:
1. DataSpace CE (Backend)
2. Simple DS GraphQL Generator (Frontend)

## Prerequisites

- Node.js v22.14.0 or later
- Java (for DataSpace CE)
- npm (Node Package Manager)

## Project Structure

```
hackathon/
├── dataspace-ce/         # Backend DataSpace CE project
└── simple-ds-gql-generator/  # Frontend React application
```

## Setting Up and Running the Projects

### 1. DataSpace CE (Backend)

1. Navigate to the backend directory:
   ```bash
   cd dataspace-ce
   ```

2. Start the DataSpace CE server:
   ```bash
   ./gradlew bootRun
   ```

   The server will start on http://localhost:8080

### 2. Simple DS GraphQL Generator (Frontend)

1. Navigate to the frontend directory:
   ```bash
   cd simple-ds-gql-generator
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Start the development server:
   ```bash
   export NODE_OPTIONS=--openssl-legacy-provider && npm start
   ```

   The application will be available at http://localhost:3000

## Environment Configuration

### Frontend (.env file)
```
DS_ENDPOINT=http://localhost:8080/graphiql
export NODE_OPTIONS=--openssl-legacy-provider
```

## Common Issues and Solutions

1. OpenSSL Error:
   If you encounter an OpenSSL-related error when starting the frontend, make sure to run the application with:
   ```bash
   export NODE_OPTIONS=--openssl-legacy-provider && npm start
   ```

2. 404 Not Found Errors:
   - Ensure the backend server is running before starting the frontend
   - Check that the `DS_ENDPOINT` in the frontend's `.env` file points to the correct backend URL

## Development Workflow

1. Start the backend server first (DataSpace CE)
2. Then start the frontend development server
3. The frontend will automatically proxy GraphQL requests to the backend

## Additional Commands

### Frontend

- Generate GraphQL code:
  ```bash
  npm run allgen
  ```

- Remove generated files:
  ```bash
  npm run rm-allgen
  ```

## Need Help?

If you encounter any issues:
1. Ensure all prerequisites are installed
2. Check that both servers are running on their respective ports
3. Verify the environment variables are set correctly
4. Check the console logs for any error messages 