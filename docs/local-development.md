# Local Development Guide

This guide will help you set up your local development environment for 2ndNature.

## Prerequisites

Before you can install and use 2ndNature, make sure you have the following installed on your computer:

### For Linux and MacOS:
- [Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)
- [Node v18](https://nodejs.org/en/download)
- [yarn v4](https://yarnpkg.com/getting-started/install)
- [nvm](https://github.com/nvm-sh/nvm/blob/master/README.md)

### For Windows (WSL):
1. Install WSL by running in PowerShell as Administrator:
```powershell
wsl --install
```
2. After restart, configure git:
```bash
sudo apt-get install git
git config --global user.name "Your Name"
git config --global user.email "youremail@domain.com"
```
3. Install nvm, node.js and yarn:
```bash
sudo apt-get install curl
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/master/install.sh | bash
nvm install
nvm use
corepack enable
```

## Step 1: Clone the Repository

```bash
git clone [your-repo-url]
cd 2ndNature
```

## Step 2: Set up PostgreSQL Database

### For Linux:
```bash
# Option 1: Local installation
sudo apt-get install postgresql
psql postgres -c "CREATE DATABASE \"default\";" -c "CREATE DATABASE test;"

# Option 2: Using Docker
make postgres-on-docker
```

### For MacOS:
```bash
# Option 1: Using Homebrew
brew install postgresql@16
export PATH="/opt/homebrew/opt/postgresql@16/bin:$PATH"
psql postgres -c "CREATE DATABASE \"default\";" -c "CREATE DATABASE test;"

# Option 2: Using Docker
make postgres-on-docker
```

### For Windows (WSL):
Follow the Linux instructions within your WSL terminal.

## Step 3: Set up Redis Database

### For Linux:
```bash
# Option 1: Local installation
sudo apt-get install redis-server

# Option 2: Using Docker
make redis-on-docker
```

### For MacOS:
```bash
# Option 1: Using Homebrew
brew install redis
brew services start redis

# Option 2: Using Docker
make redis-on-docker
```

### For Windows (WSL):
Follow the Linux instructions within your WSL terminal.

## Step 4: Configure Environment Variables

1. Copy the example environment files:
```bash
cp ./packages/twenty-front/.env.example ./packages/twenty-front/.env
cp ./packages/twenty-server/.env.example ./packages/twenty-server/.env
```

2. Update the following variables in your `.env` files:

Frontend (`packages/twenty-front/.env`):
```
REACT_APP_SERVER_BASE_URL=http://localhost:3000
```

Backend (`packages/twenty-server/.env`):
```
PG_DATABASE_URL=postgres://postgres:postgres@localhost:5432/default?connection_limit=1
REDIS_URL=redis://localhost:6379
FRONT_DOMAIN=localhost
SERVER_URL=http://localhost:3000
```

## Step 5: Install Dependencies

From the root directory:
```bash
yarn
```

## Step 6: Initialize the Database

```bash
npx nx database:reset twenty-server
```

## Step 7: Start the Development Servers

You can start all services at once:
```bash
npx nx start
```

Or start them individually:
```bash
npx nx start twenty-server
npx nx worker twenty-server
npx nx start twenty-front
```

## Accessing the Application

- Frontend: http://localhost:3001
- Backend: http://localhost:3000
- GraphQL API: http://localhost:3000/graphql
- REST API: http://localhost:3000/rest

Default login credentials:
- Email: tim@apple.dev
- Password: Applecar2025

## Troubleshooting

### Common Issues

1. **Out of Memory Error**
   If you encounter memory issues while running `npx nx start`, try:
   - In `packages/twenty-front/.env`, uncomment:
     ```
     VITE_DISABLE_TYPESCRIPT_CHECKER=true
     VITE_DISABLE_ESLINT_CHECKER=true
     ```
   - Or run only the services you need:
     ```bash
     npx nx worker twenty-server
     ```

2. **No Emails Being Sent**
   Make sure the worker is running:
   ```bash
   npx nx worker twenty-server
   ```

3. **Database Connection Issues**
   - Verify PostgreSQL is running
   - Check your database credentials in the `.env` file
   - Ensure the database exists: `psql -l` to list databases

4. **Redis Connection Issues**
   - Verify Redis is running
   - Check Redis connection URL in the `.env` file

For more troubleshooting tips, refer to the [original Twenty documentation](https://twenty.com/developers/section/self-hosting/troubleshooting). 