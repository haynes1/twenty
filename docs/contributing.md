# Contributing to 2ndNature

Thank you for your interest in contributing to 2ndNature! This document provides guidelines and instructions for contributing to the project.

## Code of Conduct

Please read and follow our [Code of Conduct](./CODE_OF_CONDUCT.md) to maintain a respectful and inclusive environment for everyone.

## Getting Started

1. Fork the repository
2. Clone your fork:
```bash
git clone https://github.com/your-username/2ndNature.git
cd 2ndNature
```
3. Set up your development environment following the [Local Development Guide](./local-development.md)
4. Create a new branch for your changes:
```bash
git checkout -b feature/your-feature-name
```

## Development Workflow

### Branch Strategy

- `main` - Production branch
- `master` - Development branch
- `alpha` - Alpha testing branch
- Feature branches - Created from `master`

### Making Changes

1. Create a feature branch from `master`
2. Make your changes
3. Write or update tests as needed
4. Ensure all tests pass
5. Submit a pull request to `master`

### Pull Request Process

1. Update the README.md with details of changes if needed
2. Update the documentation if you're changing functionality
3. The PR will be merged once you have the sign-off of at least one maintainer
4. Your changes will be auto-deployed to the test environment after merging to `master`

## Code Style

### TypeScript/JavaScript

- Use TypeScript for all new code
- Follow the existing code style
- Use meaningful variable and function names
- Add comments for complex logic
- Keep functions small and focused

### React Components

- Use functional components with hooks
- Follow the existing component structure
- Keep components focused and reusable
- Use proper prop types
- Implement error boundaries where appropriate

### CSS/Styling

- Use Emotion for styling
- Follow the existing styling patterns
- Keep styles modular and reusable
- Use CSS variables for theming

## Testing

### Frontend Tests

- Write unit tests for components
- Write integration tests for features
- Test edge cases and error states
- Ensure good test coverage

### Backend Tests

- Write unit tests for services
- Write integration tests for APIs
- Test error handling
- Ensure good test coverage

## Documentation

### Code Documentation

- Add JSDoc comments for functions and classes
- Document complex algorithms
- Keep documentation up to date
- Use clear and concise language

### API Documentation

- Document all API endpoints
- Include request/response examples
- Document error cases
- Keep documentation in sync with changes

## Commit Messages

Follow the [Conventional Commits](https://www.conventionalcommits.org/) specification:

```
<type>(<scope>): <description>

[optional body]

[optional footer]
```

Types:
- feat: A new feature
- fix: A bug fix
- docs: Documentation changes
- style: Changes that don't affect code meaning
- refactor: Code changes that neither fix bugs nor add features
- perf: Performance improvements
- test: Adding or fixing tests
- chore: Changes to build process or auxiliary tools

## Review Process

1. All PRs require at least one review
2. Address review comments promptly
3. Keep the PR focused and manageable
4. Update the PR as needed based on feedback

## Release Process

1. Changes are merged to `master`
2. Auto-deployed to test environment
3. After testing, changes can be promoted to `main`
4. Auto-deployed to production

## Getting Help

- Join our [Discord community](https://discord.gg/your-discord)
- Check the [documentation](./README.md)
- Open an issue for bugs or feature requests
- Ask questions in discussions

## Recognition

Contributors will be recognized in:
- The project's README.md
- Release notes
- Project documentation

Thank you for contributing to 2ndNature! 