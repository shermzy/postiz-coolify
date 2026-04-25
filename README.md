# Postiz Coolify Deployment

This repo holds the production Docker Compose stack for deploying Postiz to Coolify.

Target deployment:

- Host: `postiz.app.t3ai.xyz`
- Coolify project: `Postiz`
- Coolify server: `Automation`

The compose file intentionally keeps only the services required for production:

- `postiz`
- `postiz-postgres`
- `postiz-redis`
- `temporal`
- `temporal-postgresql`
- `temporal-elasticsearch`

Operational notes:

- Secrets are configured in Coolify, not committed to Git.
- `*.app.t3ai.xyz` already resolves to the Automation server.
- After first login, registration can be disabled by setting `DISABLE_REGISTRATION=true` and redeploying.
