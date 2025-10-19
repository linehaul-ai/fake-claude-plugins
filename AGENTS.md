# AGENTS.md

## Build/Lint/Test Commands
- `go fmt {file}` - Format Go files (auto-runs on save for .go files)
- `go vet {file}` - Vet Go files (auto-runs on save)
- `go test ./...` - Run all tests (runs on pre-commit)
- `go test -run TestName ./internal/tools/` - Run specific test
- `go build -o /tmp/mcp-server cmd/server/main.go` - Build MCP server (runs on pre-commit)
- `go mod tidy` - Clean dependencies (auto-runs when go.mod is created)

## Architecture & Structure
This is a Claude Code plugin repository for building HTTP MCP Servers using the MCP Go SDK. It contains:
- **agents/**: Contains `mcp-dev-go-sdk-agent.md` - specialist agent for MCP Go SDK development
- **commands/**: 9 specialized commands for generating/reviewing MCP tools, API clients, and tests
- **hooks/**: Auto-formatting, validation, and pre-commit checks via hooks.json
- **Expected project structure** (in target MCP projects): `internal/tools/`, `internal/client/`, `internal/models/`, `internal/server/`, `cmd/server/`

## Code Style Guidelines
- **Tool Registration**: Use typed pattern `mcp.AddTool[In, Out](server, *Tool, handler)` with signature `func(context.Context, *mcp.CallToolRequest, Input) (*mcp.CallToolResult, Output, error)`
- **Jsonschema Tags**: All input structs require `json` and `jsonschema` tags with `required`, `description`, and format validators (e.g., `format=email`)
- **Error Handling**: Never ignore errors; wrap with `fmt.Errorf("operation failed: %w", err)`; return Go errors directly
- **Context Propagation**: Always pass `context.Context` as first parameter; use for cancellation and timeouts
- **Stateless Handlers**: No shared state across invocations; use request-scoped servers with StreamableHTTPHandler factory
- **Naming**: Tools: `operation_entity` (e.g., `create_person`), Inputs: `OperationEntityInput`, Registration: `RegisterEntityTools(server, client)`
- **Project Structure**: Follow `internal/tools/`, `internal/client/`, `internal/models/` conventions
