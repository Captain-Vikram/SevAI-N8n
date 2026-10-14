# n8n workspace

This workspace contains a Docker Compose setup for running n8n locally.

## Prerequisites

- [Docker Desktop](https://docs.docker.com/desktop/) with Docker Compose enabled

## Start n8n

1. Optional: copy `.env.example` to `.env` and adjust the values.
2. Start the service:

   ```powershell
   docker compose up -d
   ```

3. Open [http://localhost:5678](http://localhost:5678).
4. Complete n8n's first-run owner setup in the browser.

The `n8n_data` named volume persists workflows, credentials, and other n8n data across container restarts.

## Useful commands

```powershell
# Follow logs
docker compose logs -f n8n

# Stop the service without deleting data
docker compose down

# Stop the service and remove the persisted n8n volume
docker compose down -v
```

For a hosted deployment, set `N8N_HOST`, `N8N_PROTOCOL`, and `WEBHOOK_URL` to match the reverse proxy or domain before starting the service. Do not expose the local HTTP configuration directly to the internet.

## Combine documentation

To combine every Markdown and other supported text document under `docs\` (including nested folders) into one file:

```powershell
node .\combine-docs.js
```

The default output is `combined-docs.md`. You can provide a different input directory and output file:

```powershell
node .\combine-docs.js .\docs .\documentation-all.md
```

Supported file types are `.md`, `.markdown`, `.txt`, and `.toon`.
