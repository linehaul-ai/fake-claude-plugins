<!-- fake-claude-plugins/commands/generate-mcp-tool.md -->
---
description: Generate a new MCP tool file from template
argument-hint: [entity-name]
---

@mcp-dev-go-sdk-agent Create a new tool file at `internal/tools/$1.go` for the entity '$1'.

**Include these operations:**
- `create_$1`
- `get_$1`
- `update_$1`
- `list_$1`
- `delete_$1`

**Follow the exact pattern from internal/tools/people.go:**
- Proper Input/Output structs with jsonschema tags
- Type-safe handlers using `mcp.AddTool[In, Out]`
- Integration with twentyClient
- `Register$1Tools(server, client)` function

**Create the complete implementation** and then remind me to:
1. Add the entity model to `internal/models/types.go`
2. Register tools in `internal/server/server.go`
3. Add Twenty CRM client methods in `internal/client/twenty_client.go`
