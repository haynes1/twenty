# Architecture Overview

2ndNature is built on top of Twenty CRM's architecture, which is a modern, full-stack application using a microservices-like approach within a monorepo structure.

## Tech Stack

- **Frontend**: React with Recoil for state management and Emotion for styling
- **Backend**: NestJS with PostgreSQL and Redis
- **Build System**: Nx for monorepo management
- **Package Manager**: Yarn
- **Database**: PostgreSQL
- **Cache**: Redis
- **API**: GraphQL and REST endpoints

## Project Structure

The project is organized as a monorepo using Nx, with the following main packages:

```
packages/
├── twenty-front/          # Frontend React application
├── twenty-server/         # Backend NestJS application
├── twenty-emails/         # Email templates
├── twenty-chrome-extension/ # Chrome extension for LinkedIn integration
└── twenty-website/        # Marketing website
```

## Key Components

### Frontend (`twenty-front`)

The frontend is a React application that provides the user interface for the CRM. Key features include:

- Modern, responsive UI built with React
- State management using Recoil
- Styling with Emotion
- Real-time updates using WebSocket connections
- Rich text editing capabilities
- Data grid for efficient data display

### Backend (`twenty-server`)

The backend is a NestJS application that handles:

- Data persistence with PostgreSQL
- Caching with Redis
- Authentication and authorization
- API endpoints (GraphQL and REST)
- Background jobs and workers
- File storage
- Email sending

### Database Schema

The application uses PostgreSQL with the following main entities:

- Companies
- People
- Opportunities
- Activities
- Tasks
- Notes
- Files
- Users
- Workspaces

## Development Workflow

### Branch Strategy

- `main` - Production branch
- `master` - Development branch
- `alpha` - Alpha testing branch
- Feature branches - Created from `master`

### Deployment Pipeline

1. Feature branches are created from `master`
2. Changes are reviewed and merged to `master`
3. `master` is auto-deployed to the test environment
4. After testing, changes can be promoted to `main`
5. `main` is auto-deployed to production

## API Documentation

### GraphQL API

The GraphQL API is available at `/graphql` and provides:

- Real-time data updates
- Strongly typed queries and mutations
- Efficient data fetching
- Built-in documentation

### REST API

The REST API is available at `/rest` and provides:

- Traditional REST endpoints
- Standard HTTP methods
- JSON request/response format

## Authentication

The application supports multiple authentication methods:

- Email/Password
- Google OAuth
- Microsoft OAuth
- API Keys for external integrations

## Extensions and Integrations

2ndNature supports various integrations:

- Chrome Extension for LinkedIn
- Email providers (Gmail, Outlook)
- Calendar integrations
- File storage providers
- Webhook support for external systems

## Performance Considerations

- Redis caching for frequently accessed data
- Database indexing for optimal query performance
- Frontend code splitting and lazy loading
- Background workers for heavy tasks
- Rate limiting for API endpoints

## Security

- JWT-based authentication
- Role-based access control
- API rate limiting
- Input validation
- SQL injection prevention
- XSS protection
- CORS configuration

## Monitoring and Logging

- Application logs
- Error tracking
- Performance monitoring
- User activity tracking
- Database query monitoring

## Future Considerations

As we continue to develop 2ndNature, we plan to:

1. Enhance the plugin system
2. Improve the API extensibility
3. Add more integration options
4. Optimize performance further
5. Enhance the security features 