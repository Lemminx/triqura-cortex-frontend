# Triqura Cortex Platform - Frontend

Frontend web application for the Triqura Cortex Platform, deployed to Azure App Service.

## 🚀 Deployment

This repository deploys automatically to Azure App Service via GitHub Actions when code is pushed to the `main` branch.

**Target Azure Resource:**
- App Service: `app-triqura-frontend-dev`
- Region: France Central
- Runtime: Node.js 20 LTS

## 🔧 Required GitHub Secrets

To enable automatic deployment, configure the following secrets in **Settings → Secrets and variables → Actions**:

| Secret Name | Value | Description |
|-------------|-------|-------------|
| `AZURE_CLIENT_ID` | `4e19a093-339d-469f-9e0a-8fdb8be595f8` | Service principal client ID |
| `AZURE_TENANT_ID` | `7ab18733-3bdb-46c7-8972-da698cb49590` | Azure tenant ID |
| `AZURE_SUBSCRIPTION_ID` | `ce2250e3-8d85-45d8-9695-bebc72e5811c` | Azure subscription ID |
| `AZURE_WEBAPP_NAME` | `app-triqura-frontend-dev` | Target App Service name |

### How to Add Secrets

1. Navigate to: https://github.com/Lemminx/triqura-cortex-frontend/settings/secrets/actions
2. Click **"New repository secret"**
3. Add each secret with the exact name and value from the table above
4. Click **"Add secret"** to save

## 📋 Project Structure

```
triqura-cortex-frontend/
├── .github/
│   └── workflows/
│       └── deploy.yml          # GitHub Actions deployment pipeline
├── src/                        # Application source code
├── public/                     # Static assets
├── package.json                # Dependencies and scripts
└── README.md                   # This file
```

## 🏗️ Local Development

```bash
# Install dependencies
npm install

# Start development server
npm run dev

# Build for production
npm run build

# Run tests
npm test
```

## 🔗 Backend API

The frontend connects to the backend API at:
- **Development**: `https://app-triqura-backend-dev.azurewebsites.net`

## 🔐 Authentication

GitHub Actions uses **OpenID Connect (OIDC)** for passwordless authentication to Azure. No client secrets are stored in GitHub.

Federated credential subject: `repo:Lemminx/triqura-cortex-frontend:ref:refs/heads/main`

## 📚 Related Documentation

- **Backend Repository**: https://github.com/Lemminx/triqura-cortex-backend
- **Infrastructure Repository**: https://github.com/Lemminx/triqura-cortex-platform
- **CI/CD Documentation**: [cicd-implementation-plan.md](https://github.com/Lemminx/triqura-cortex-platform/blob/main/docs/build/cicd-implementation-plan.md)

---

**Last Updated:** March 5, 2026
