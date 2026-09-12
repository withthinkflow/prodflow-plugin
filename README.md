# prodflow-plugin

Claude Code plugin for [ProdFlow](https://github.com/withthinkflow/prodflow-master). Wraps the `POST /mcp` endpoint.

```
export PRODFLOW_TOKEN=pf_…                 # workspace → MCP page → New token
export PRODFLOW_URL=https://your.host/api  # optional; default http://localhost:3000 (Nest direct, no /api)

claude
/plugin marketplace add withthinkflow/prodflow-plugin
/plugin install prodflow@prodflow
```

`PRODFLOW_URL` is the API origin, `/mcp` is appended. Behind the Vite proxy or a hosted deploy that is `<origin>/api`.
