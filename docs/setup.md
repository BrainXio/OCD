# OCD Setup

## Install

```bash
cd ocd
uv pip install -e .
```

## Join the Shared Bus

```bash
export ADHD_BUS_REPO_SLUG=projects
```

OCD posts enforcement results (mode switches, gate passes/failures) to the ADHD
bus for audit and cross-agent visibility.

## MCP Server

```json
{
  "mcpServers": {
    "ocd": {
      "command": "bash",
      "args": [
        "-c",
        "uv --directory /home/mrrobot0985/work/projects/ocd run ocd-mcp"
      ]
    },
    "adhd": {
      "command": "bash",
      "args": [
        "-c",
        "ADHD_BUS_REPO_SLUG=projects uv --directory /home/mrrobot0985/work/projects/adhd run adhd-mcp"
      ]
    }
  }
}
```

Full workspace guide: `../SETUP.md`
