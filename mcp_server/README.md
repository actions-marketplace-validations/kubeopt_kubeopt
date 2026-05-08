# kubeopt-mcp

MCP server for [KubeOpt](https://github.com/kubeopt/kubeopt) — query Kubernetes cluster costs from Claude, Cursor, or Windsurf.

## Setup

Add to your Claude Desktop config (`~/.claude/claude_desktop_config.json`):

```json
{
  "mcpServers": {
    "kubeopt": {
      "command": "uvx",
      "args": ["kubeopt-mcp"],
      "env": {
        "KUBEOPT_API_URL": "https://your-kubeopt-instance.com",
        "KUBEOPT_USERNAME": "kubeopt",
        "KUBEOPT_PASSWORD": "your-password"
      }
    }
  }
}
```

Requires a running KubeOpt instance. See [kubeopt/kubeopt](https://github.com/kubeopt/kubeopt) to self-host.

## Tools

| Tool | What it does |
|------|-------------|
| `list_clusters` | List all monitored clusters with cost data |
| `get_cost_summary` | Portfolio-level cost summary across all clusters |
| `get_cluster_analysis` | Detailed analysis for a specific cluster |
| `get_recommendations` | Actionable recommendations sorted by savings impact |
| `analyze_cluster` | Trigger a fresh analysis and poll until complete |
| `get_pod_costs` | Per-pod cost breakdown, filterable by namespace |
