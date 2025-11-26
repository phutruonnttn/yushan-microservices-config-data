# Yushan Microservices Config Data

> 📁 **Centralized Configuration Repository** - Git-based configuration storage for Yushan Platform microservices

## 📋 Overview

This repository contains all configuration files for Yushan Platform microservices. The Config Server reads configurations from this repository and serves them to business services.

## 🏗️ Architecture

```
Business Services → Config Server → Config Repo (this repo)
```

- **Config Repo (this repo)**: Stores all configuration files
- **Config Server**: Reads from this repo and serves via REST API
- **Business Services**: Pull config from Config Server on startup

## 📁 Structure

```
yushan-microservices-config-data/
├── configs/
│   ├── user-service.yml
│   ├── content-service.yml
│   ├── engagement-service.yml
│   ├── gamification-service.yml
│   └── analytics-service.yml
└── README.md
```

## 🔧 Configuration Files

Each service has its own configuration file:

- **user-service.yml** - User Service configuration
- **content-service.yml** - Content Service configuration
- **engagement-service.yml** - Engagement Service configuration
- **gamification-service.yml** - Gamification Service configuration
- **analytics-service.yml** - Analytics Service configuration

## 🚀 Workflow

### When you need to update a service configuration:

1. **Edit config file** in this repository (on GitHub or locally)
2. **Commit and push** changes to GitHub
3. **Config Server** automatically fetches the latest config from this repo
4. **Restart the business service** to pull the new configuration

### Example: Update Content Service config

```bash
# 1. Edit configs/content-service.yml
# 2. Commit and push
git add configs/content-service.yml
git commit -m "Update content service database URL"
git push origin main

# 3. Config Server will automatically fetch the new config
# 4. Restart content-service to apply changes
```

## 🔐 Security

- This repository should be **private** (contains sensitive configuration)
- Use environment variables for secrets (don't commit passwords directly)
- Use GitHub secrets for CI/CD pipelines

## 📝 Best Practices

1. **Never commit secrets directly** - Use environment variables or secrets management
2. **Use meaningful commit messages** - Document what changed and why
3. **Test changes in dev/staging** before applying to production
4. **Review changes** before merging to main branch
5. **Keep configs organized** - One file per service

## 🔗 Related Repositories

- **Config Server**: [yushan-microservices-config-server](https://github.com/phutruonnttn/yushan-microservices-config-server)
- **Platform Documentation**: [yushan-platform-docs](https://github.com/phutruonnttn/yushan-platform-docs)

## 📄 License

This repository is part of the Yushan Platform ecosystem.

---

**Yushan Config Repository** - Centralized configuration management for microservices 📁

