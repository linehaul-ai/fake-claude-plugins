<!-- fake-claude-plugins/commands/fix-mcp-patterns.md -->
---
description: Auto-fix common MCP Go SDK pattern violations in current file
---

@mcp-dev-go-sdk-agent Scan the current file and fix these common violations:

## Fixes to Apply

1. **Missing CallToolResult**: Add `&mcp.CallToolResult{}` to returns
2. **Handler Signatures**: Correct to `func(context.Context, *mcp.CallToolRequest, In) (*mcp.CallToolResult, Out, error)`
3. **Missing Context**: Add `context.Context` as first parameter
4. **Jsonschema Tags**: Add missing `description` tags to all input fields
5. **Error Returns**: Ensure all errors are properly returned, never ignored

**Show clear before/after diff for each fix made.**

If no issues found, confirm file follows all MCP Go SDK best practices.
