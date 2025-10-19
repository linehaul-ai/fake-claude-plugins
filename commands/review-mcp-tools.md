<!-- fake-claude-plugins/commands/review-mcp-tools.md -->
---
description: Review all MCP tool implementations for proper patterns and conventions
---

@mcp-dev-go-sdk-agent Please review all files in internal/tools/ and check for:

1. **Handler Signatures**: Verify proper `func(context.Context, *mcp.CallToolRequest, InputType) (*mcp.CallToolResult, OutputType, error)` pattern
2. **Jsonschema Tags**: Check all input structs have proper validation (required, format, pattern, description)
3. **Context Propagation**: Ensure context.Context is passed through all layers
4. **Error Handling**: Validate proper error returns and handling
5. **Type Safety**: Confirm typed inputs/outputs are used correctly

Provide a summary of issues found across all tools with priority levels (Critical/High/Medium/Low).
