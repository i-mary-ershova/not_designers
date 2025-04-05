# Hackathon Project Setup

This repository contains two main projects:
1. DataSpace CE (Backend)
2. Simple DS GraphQL Generator (Frontend)

## Prerequisites

- Java (for DataSpace CE)


## Initial Setup

### Git Configuration


2. Clone the repository:
   ```bash
   # Using SSH (recommended)
   git clone git@github.com:i-mary-ershova/not_designers.git
   # OR using HTTPS
   git clone https://github.com/i-mary-ershova/not_designers.git
   ```

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

3. Start the development server (choose ONE of these methods):

   Option A - Using environment variable (if not using Cursor IDE):
   ```bash
   export NODE_OPTIONS=--openssl-legacy-provider && npm start
   ```

   Option B - Using package.json script (works in all IDEs):
   ```bash
   npm run start:legacy
   ```

   Option C - Downgrade Node.js version (alternative solution):
   ```bash
   # Using nvm (Node Version Manager)
   nvm install 16
   nvm use 16
   npm start
   ```

   The application will be available at http://localhost:3000

## Environment Configuration

### Frontend (.env file)
```
DS_ENDPOINT=http://localhost:8080/graphiql
```

## Common Issues and Solutions

1. OpenSSL Error:
   If you encounter OpenSSL-related errors, try these solutions in order:
   - Use `npm run start:legacy` (recommended)
   - Downgrade to Node.js v16
   - Use a different IDE if the above solutions don't work

2. Git Authentication Errors:
   - Ensure you've set up SSH keys correctly
   - Or use HTTPS with a personal access token
   - Check your Git configuration: `git config --list`

3. 404 Not Found Errors:
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