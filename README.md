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
- Redis is internal-only on the Coolify network and runs without auth in this stack.
- `*.app.t3ai.xyz` already resolves to the Automation server.
- After first login, registration can be disabled by setting `DISABLE_REGISTRATION=true` and redeploying.
- For Azure OpenAI, configure `OPENAI_BASE_URL` as `https://<resource>.openai.azure.com/openai/v1/` and set the Postiz model env vars to Azure deployment names, not raw model family names. For example, if Azure shows deployment `gpt-5.5-1` for model `gpt-5.5`, Postiz should use `OPENAI_TEXT_MODEL=gpt-5.5-1`.
