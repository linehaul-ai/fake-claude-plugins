<!-- fake-claude-plugins/commands/validate-mcp-server.md -->
---
description: Validate overall MCP server architecture and configuration
---

@mcp-dev-go-sdk-agent Perform comprehensive validation:

## Structure Validation
1. **Tool Registration**: Check all tools are registered in `internal/server/server.go`
2. **Model Definitions**: Verify all models exist in `internal/models/types.go`
3. **HTTP Handler**: Ensure `main.go` properly initializes StreamableHTTPHandler
4. **Graceful Shutdown**: Validate handler.Close() called before server.Shutdown()
5. **Environment Variables**: Check all env vars are loaded and used correctly

## Code Quality Checks
- No hardcoded credentials or URLs
- Proper context usage throughout
- Error handling consistency
- Logging setup and usage
- Test coverage for tools

Report any architectural issues, missing pieces, or anti-patterns found.
