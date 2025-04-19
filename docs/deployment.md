# Deployment Guide

This guide explains how to deploy 2ndNature to different environments. We support multiple deployment options to accommodate different needs and infrastructure preferences.

## Deployment Options

1. Docker Compose (Recommended for self-hosting)
2. Kubernetes
3. Manual deployment

## Environment Setup

Before deploying, ensure you have the following environment variables configured:

### Required Variables

```env
# Database
PG_DATABASE_URL=postgresql://user:password@host:5432/database
PG_SSL_ALLOW_SELF_SIGNED=false

# Redis
REDIS_URL=redis://localhost:6379

# Server
FRONT_DOMAIN=your-domain.com
SERVER_URL=https://your-domain.com
PORT=3000

# Security
APP_SECRET=your-secret-key
ACCESS_TOKEN_EXPIRES_IN=30m
LOGIN_TOKEN_EXPIRES_IN=15m
REFRESH_TOKEN_EXPIRES_IN=90d
```

### Optional Variables

```env
# Email
EMAIL_DRIVER=smtp
EMAIL_SMTP_HOST=smtp.example.com
EMAIL_SMTP_PORT=587
EMAIL_SMTP_USER=your-email
EMAIL_SMTP_PASSWORD=your-password

# Storage
STORAGE_TYPE=s3
STORAGE_S3_REGION=your-region
STORAGE_S3_NAME=your-bucket
STORAGE_S3_ACCESS_KEY_ID=your-key
STORAGE_S3_SECRET_ACCESS_KEY=your-secret

# Monitoring
SENTRY_DSN=your-sentry-dsn
```

## Docker Compose Deployment

### Prerequisites

- Docker
- Docker Compose
- 2GB+ RAM
- Domain name (for production)

### Steps

1. Clone the repository:
```bash
git clone https://github.com/your-username/2ndNature.git
cd 2ndNature
```

2. Create environment file:
```bash
cp packages/twenty-docker/.env.example .env
```

3. Generate secrets:
```bash
# Generate APP_SECRET
openssl rand -base64 32

# Set PostgreSQL password
echo "PGPASSWORD_SUPERUSER=your-strong-password" >> .env
```

4. Start the application:
```bash
docker compose up -d
```

5. Access the application at http://localhost:3000

## Kubernetes Deployment

### Prerequisites

- Kubernetes cluster
- kubectl
- Helm (optional)

### Steps

1. Create namespace:
```bash
kubectl create namespace 2ndnature
```

2. Create secrets:
```bash
kubectl create secret generic -n 2ndnature tokens \
  --from-literal accessToken=your-token \
  --from-literal loginToken=your-token \
  --from-literal refreshToken=your-token \
  --from-literal fileToken=your-token
```

3. Apply configurations:
```bash
kubectl apply -f k8s/
```

4. Monitor deployment:
```bash
kubectl get pods -n 2ndnature
```

## Manual Deployment

### Prerequisites

- Node.js v18
- PostgreSQL
- Redis
- PM2 (recommended)

### Steps

1. Clone and install dependencies:
```bash
git clone https://github.com/your-username/2ndNature.git
cd 2ndNature
yarn
```

2. Build the application:
```bash
# Build frontend
npx nx build twenty-front

# Build backend
npx nx build twenty-server
```

3. Start the services:
```bash
# Start backend
npx nx start twenty-server

# Start worker
npx nx worker twenty-server

# Start frontend
npx nx start twenty-front
```

## SSL Configuration

For production deployments, SSL is required. Here are the steps to configure SSL:

1. Obtain SSL certificates (Let's Encrypt recommended)
2. Configure your reverse proxy (Nginx/Apache)
3. Update environment variables:
```env
SERVER_URL=https://your-domain.com
```

## Monitoring

### Logging

- Application logs are available in the container logs
- Use `docker logs` or `kubectl logs` to view logs
- Configure log aggregation for production

### Health Checks

- Backend health check: `/health`
- Frontend health check: `/health`
- Monitor these endpoints in production

## Backup and Recovery

### Database Backup

1. Regular PostgreSQL backups:
```bash
pg_dump -U your-user -d your-database > backup.sql
```

2. Automated backup script:
```bash
#!/bin/bash
BACKUP_DIR="/path/to/backups"
TIMESTAMP=$(date +%Y%m%d_%H%M%S)
pg_dump -U your-user -d your-database > "$BACKUP_DIR/backup_$TIMESTAMP.sql"
```

### Recovery

1. Stop the application
2. Restore the database:
```bash
psql -U your-user -d your-database < backup.sql
```
3. Restart the application

## Scaling

### Horizontal Scaling

- Use multiple worker instances
- Configure load balancing
- Use Redis for session storage
- Implement database replication

### Vertical Scaling

- Increase container resources
- Optimize database performance
- Configure caching
- Use CDN for static assets

## Troubleshooting

### Common Issues

1. Database Connection
   - Check credentials
   - Verify network connectivity
   - Check PostgreSQL logs

2. Redis Connection
   - Verify Redis is running
   - Check connection string
   - Monitor Redis memory usage

3. Memory Issues
   - Monitor container memory usage
   - Adjust resource limits
   - Optimize application performance

### Support

For deployment issues:
1. Check the logs
2. Review configuration
3. Consult documentation
4. Open an issue on GitHub 