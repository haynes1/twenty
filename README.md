# 2ndNature - A Fork of Twenty CRM

2ndNature is a customized fork of [Twenty CRM](https://github.com/twentyhq/twenty), an open-source CRM platform. This fork aims to extend and enhance the original Twenty CRM with additional features and customizations.

## About Twenty CRM

Twenty is an open-source CRM that was built with three main principles in mind:

1. **Affordability**: CRMs shouldn't be expensive, and users shouldn't be trapped in expensive solutions.
2. **Modern UX**: Built with inspiration from modern tools like Notion, Airtable, and Linear.
3. **Open Source**: Community-driven development with a focus on extensibility.

For more information about the original Twenty CRM, please visit their [official documentation](https://twenty.com/developers).

## Development Workflow

### Branch Strategy

- `main` - Production branch, auto-deployed to the main site
- `master` - Development branch, auto-deployed to the test environment
- `alpha` - Alpha branch, auto-deployed to the alpha environment
- Feature branches should be created from `master` and merged via pull requests

### Development Process

1. Create a feature branch from `master`
2. Make your changes
3. Submit a pull request to `master`
4. After review and approval, changes will be merged and auto-deployed to the test environment
5. Once tested, changes can be promoted to `main` via pull request

## Getting Started

### Local Development Setup

For detailed instructions on setting up your local development environment, please refer to our [Local Development Guide](./docs/local-development.md).

### Quick Start

1. Clone the repository:
```bash
git clone [your-repo-url]
cd 2ndNature
```

2. Install dependencies:
```bash
yarn
```

3. Set up your environment variables:
```bash
cp ./packages/twenty-front/.env.example ./packages/twenty-front/.env
cp ./packages/twenty-server/.env.example ./packages/twenty-server/.env
```

4. Start the development servers:
```bash
npx nx start
```

The application will be available at:
- Frontend: http://localhost:3001
- Backend: http://localhost:3000

## Documentation

- [Local Development Guide](./docs/local-development.md)
- [Architecture Overview](./docs/architecture.md)
- [Contributing Guidelines](./docs/contributing.md)
- [Deployment Guide](./docs/deployment.md)

## License

This project is licensed under the same terms as the original Twenty CRM. See the [LICENSE](./LICENSE) file for details.

<br>
<p align="center">
  <a href="https://www.twenty.com">
    <img src="./packages/twenty-website/public/images/core/logo.svg" width="100px" alt="Twenty logo" />
  </a>
</p>

<h2 align="center" >The #1 Open-Source CRM </h3>

<p align="center"><a href="https://twenty.com">🌐 Website</a> · <a href="https://twenty.com/developers">📚 Documentation</a> · <a href="https://github.com/orgs/twentyhq/projects/1"><img src="./packages/twenty-website/public/images/readme/planner-icon.svg" width="12" height="12"/> Roadmap </a> · <a href="https://discord.gg/cx5n4Jzs57"><img src="./packages/twenty-website/public/images/readme/discord-icon.svg" width="12" height="12"/> Discord</a> · <a href="https://www.figma.com/file/xt8O9mFeLl46C5InWwoMrN/Twenty"><img src="./packages/twenty-website/public/images/readme/figma-icon.png"  width="12" height="12"/>  Figma</a><p>
<br />


<p align="center">
  <a href="https://www.twenty.com">
    <picture>
      <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/twentyhq/twenty/v0.12.0/packages/twenty-docs/static/img/preview-dark.png">
      <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/twentyhq/twenty/v0.12.0/packages/twenty-docs/static/img/preview-light.png">
      <img src="./packages/twenty-docs/static/img/preview-light.png" alt="Companies view" />
    </picture>
  </a>
</p>

<br>

# Installation 

See:  
🚀 [Self-hosting](https://twenty.com/developers/section/self-hosting)  
🖥️ [Local Setup](https://twenty.com/developers/local-setup)  

# Does the world need another CRM?

We built Twenty for three reasons:

**CRMs are too expensive, and users are trapped.** Companies use locked-in customer data to hike prices. It shouldn't be that way.

**A fresh start is required to build a better experience.** We can learn from past mistakes and craft a cohesive experience inspired by new UX patterns from tools like Notion, Airtable or Linear.

**We believe in Open-source and community.** Hundreds of developers are already building Twenty together. Once we have plugin capabilities, a whole ecosystem will grow around it.

<br>

# What You Can Do With Twenty
We're currently developing Twenty's beta version.  

Please feel free to flag any specific needs you have by creating an issue.   

Below are a few features we have implemented to date:

+ [Add, filter, sort, edit, and track customers](#add-filter-sort-edit-and-track-customers)
+ [Create one or several opportunities for each company](#create-one-or-several-opportunities-for-each-company)
+ [See rich notes tasks displayed in a timeline](#see-rich-notes-tasks-displayed-in-a-timeline)
+ [Create tasks on records](#create-tasks-on-records)
+ [Navigate quickly through the app using keyboard shortcuts and search](#navigate-quickly-through-the-app-using-keyboard-shortcuts-and-search)


## Add, filter, sort, edit, and track customers:

<p align="center">
    <picture>
      <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/twentyhq/twenty/v0.12.0/packages/twenty-docs/static/img/index-dark.png">
      <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/twentyhq/twenty/v0.12.0/packages/twenty-docs/static/img/index-light.png">
      <img src="./packages/twenty-docs/static/img/visualise-customer-light.png" alt="Companies view" />
    </picture>
</p>

## Create one or several opportunities for each company:

<p align="center">
    <picture>
      <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/twentyhq/twenty/v0.12.0/packages/twenty-docs/static/img/kanban-dark.png">
      <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/twentyhq/twenty/v0.12.0/packages/twenty-docs/static/img/kanban-light.png">
      <img src="./packages/twenty-docs/static/img/follow-your-deals-light.png" alt="Companies view" />
    </picture>
</p>

## Track deals effortlessly with the email integration:

<p align="center">
    <picture>
      <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/twentyhq/twenty/v0.12.0/packages/twenty-docs/static/img/emails-dark.png">
      <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/twentyhq/twenty/v0.12.0/packages/twenty-docs/static/img/emails-light.png">
      <img src="./packages/twenty-docs/static/img/rich-notes-light.png" alt="Companies view" />
    </picture>
</p>

## Tailor your data model to meet business needs:

<p align="center">
    <picture>
      <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/twentyhq/twenty/v0.12.0/packages/twenty-docs/static/img/data-dark.png">
      <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/twentyhq/twenty/v0.12.0/packages/twenty-docs/static/img/data-light.png">
      <img src="./packages/twenty-docs/static/img/rich-notes-light.png" alt="Companies view" />
    </picture>
</p>

## See rich notes displayed in a timeline:

<p align="center">
    <picture>
      <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/twentyhq/twenty/v0.12.0/packages/twenty-docs/static/img/notes-dark.png">
      <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/twentyhq/twenty/v0.12.0/packages/twenty-docs/static/img/notes-light.png">
      <img src="./packages/twenty-docs/static/img/rich-notes-light.png" alt="Companies view" />
    </picture>
</p>

## Create tasks on records

<p align="center">
    <picture>
      <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/twentyhq/twenty/v0.12.0/packages/twenty-docs/static/img/tasks-dark.png">
      <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/twentyhq/twenty/v0.12.0/packages/twenty-docs/static/img/tasks-light.png">
      <img src="./packages/twenty-docs/static/img/create-tasks-light.png" alt="Companies view" />
    </picture>
</p>

## Navigate quickly through the app using keyboard shortcuts and search:

<p align="center">
    <picture>
      <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/twentyhq/twenty/v0.12.0/packages/twenty-docs/static/img/keyboard-dark.png">
      <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/twentyhq/twenty/v0.12.0/packages/twenty-docs/static/img/keyboard-light.png">
      <img src="./packages/twenty-docs/static/img/shortcut-navigation-light.png" alt="Companies view" />
    </picture>
</p>

## Connect your CRM to all your tools through our APIs and Webhooks.

<p align="center">
    <picture>
      <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/twentyhq/twenty/v0.12.0/packages/twenty-docs/static/img/api-dark.png">
      <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/twentyhq/twenty/v0.12.0/packages/twenty-docs/static/img/api-light.png">
      <img src="./packages/twenty-docs/static/img/shortcut-navigation-light.png" alt="Companies view" />
    </picture>
</p>


<br>

# Stack
- [TypeScript](https://www.typescriptlang.org/)
- [Nx](https://nx.dev/)
- [NestJS](https://nestjs.com/), with [BullMQ](https://bullmq.io/), [PostgreSQL](https://www.postgresql.org/), [Redis](https://redis.io/)
- [React](https://reactjs.org/), with [Recoil](https://recoiljs.org/) and [Emotion](https://emotion.sh/)
- [Greptile](https://greptile.com) for code reviews.
- [Lingui](https://lingui.dev/) and [Crowdin](https://twenty.crowdin.com/twenty) for translations.


# Join the Community

- Star the repo
- Subscribe to releases (watch -> custom -> releases)
- Follow us on [Twitter](https://twitter.com/twentycrm) or [LinkedIn](https://www.linkedin.com/company/twenty/) 
- Join our [Discord](https://discord.gg/cx5n4Jzs57)
- Improve translations on [Crowdin](https://twenty.crowdin.com/twenty) 
- [Contributions](https://github.com/twentyhq/twenty/contribute) are, of course, most welcome! 




