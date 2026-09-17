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

## Flow tools

`list_flows`, `get_flow`, `create_flow`, `update_flow` read and write draw.io diagrams in a project's Flow & Wireframe section. `get_flow` returns plain `<mxGraphModel>` xml even when draw.io stored it compressed; send the whole document back with `update_flow`.

## Wiki

The wiki is the project's second brain: the agent maintains it, humans read
and correct. `get_wiki_schema` returns the conventions; `list_wiki_activity`
is the log; `lint_wiki` the health check.

- `/prodflow:wiki-file` files the current conversation: entity pages
  updated, concept pages created, one page tagged #session linking everything.
- `/prodflow:wiki-lint` runs the health check and fixes what it can.
