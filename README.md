# BigQuery MCP Server by Insightful Pipe

[![MCP Compatible](https://img.shields.io/badge/MCP-Compatible-blue)](https://insightfulpipe.com/mcp-servers/bigquery)
[![Insightful Pipe](https://img.shields.io/badge/Insightful_Pipe-MCP_Servers-purple)](https://insightfulpipe.com/mcp-servers)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

> **Connect BigQuery to AI assistants: datasets, schemas and SQL on Google Cloud.**

Part of the [Insightful Pipe MCP Server Collection](https://insightfulpipe.com/mcp-servers) — use BigQuery from Claude, ChatGPT, Cursor, and other AI assistants through the Model Context Protocol (MCP).

<img src="images/bigquery-icon.svg" alt="BigQuery MCP Server" width="64" height="64">

## MCP Server URL

```
https://bigquery.insightfulmcp.com/
```

## What is BigQuery MCP?

BigQuery MCP is a **remote Model Context Protocol server** hosted by InsightfulPipe. Query BigQuery datasets, list tables, inspect schemas, and run SQL on your connected Google Cloud projects. The roles you grant the service account in GCP decide whether the connection is read-only or read & write.

## Installation

### Claude

1. Copy the MCP Server URL: `https://bigquery.insightfulmcp.com/`
2. Open [Claude Connectors Settings](https://claude.ai/settings/connectors)
3. Scroll to the bottom and click **Add custom connector**
4. Paste the URL and click **Add**
5. Click **Connect** on the connector to start authorization
6. Click **Authorize access** in the browser to complete the connection

### ChatGPT

Custom MCP servers are added through ChatGPT's **Developer mode**. Availability depends on your ChatGPT plan, and workspace admins may need to allow it.

1. Turn on **Developer mode** in ChatGPT settings
2. Create a new app for a remote MCP server and paste the URL: `https://bigquery.insightfulmcp.com/`
3. Authorize with your InsightfulPipe account

See OpenAI's guide: [Developer mode and MCP apps in ChatGPT](https://help.openai.com/en/articles/12584461-developer-mode-and-mcp-apps-in-chatgpt)

### Claude Code

```bash
claude mcp add --transport http bigquery https://bigquery.insightfulmcp.com/
```

### Cursor

Add the server to `~/.cursor/mcp.json` (all projects) or `.cursor/mcp.json` (one project):

```json
{
  "mcpServers": {
    "bigquery": {
      "url": "https://bigquery.insightfulmcp.com/"
    }
  }
}
```

Then authorize the connection when Cursor prompts you.

## Available Actions

5 actions: 4 read, 1 write.

### Read Actions (4)

| Action | Description |
|--------|-------------|
| `get_table_metadata` | Get full metadata for a table or view: schema, row count, size, partitioning, expiration |
| `get_table_schema` | Get the schema (column names + types) for a table or view |
| `list_datasets` | List all datasets in the connected Google Cloud project |
| `list_tables` | List all tables and views in a dataset |

### Write Actions (1)

| Action | Description |
|--------|-------------|
| `run_query` | Execute a Standard SQL query and return rows |

## Usage Examples

```
"List the datasets in my project"
```

```
"Show the schema of the events table"
```

```
"Run a query for daily sessions over the last 30 days"
```

## Explore More MCP Servers by Insightful Pipe

Visit **[insightfulpipe.com/mcp-servers](https://insightfulpipe.com/mcp-servers)** to discover our full collection of MCP servers.

- [PostgreSQL MCP](https://insightfulpipe.com/mcp-servers/postgresql)
- [MySQL MCP](https://insightfulpipe.com/mcp-servers/mysql)
- [SQL Server MCP](https://insightfulpipe.com/mcp-servers/mssql)

**[View All MCP Servers →](https://insightfulpipe.com/mcp-servers)**

## Resources

- [Documentation](https://insightfulpipe.com/docs)
- [Video Tutorial](https://www.youtube.com/playlist?list=PLJNzvjxzI5Xwe__BJJLAelSF0ewO3mEFk)
- [InsightfulPipe Blog](https://insightfulpipe.com/blog)

## Support

- **Documentation**: [insightfulpipe.com/docs](https://insightfulpipe.com/docs)
- **All MCP Servers**: [insightfulpipe.com/mcp-servers](https://insightfulpipe.com/mcp-servers)
- **Email**: support@insightfulpipe.com

---

**[Insightful Pipe](https://insightfulpipe.com)** — AI-powered marketing analytics through MCP servers. [Explore all integrations →](https://insightfulpipe.com/mcp-servers)

## License

MIT License - see [LICENSE](LICENSE) for details.
