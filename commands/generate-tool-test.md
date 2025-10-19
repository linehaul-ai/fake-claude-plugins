<!-- fake-claude-plugins/commands/generate-tool-test.md -->
---
description: Create comprehensive table-driven test for an MCP tool
argument-hint: [tool-name]
---

@mcp-dev-go-sdk-agent Create a comprehensive test file at `internal/tools/$1_test.go` for the '$1' tool.

## Test Coverage Required

### Test Structure
- Table-driven test pattern
- Test fixtures and helpers
- Mock Twenty CRM API responses

### Test Cases
1. **Happy Path**: Successful operations with valid data
2. **Error Cases**: API errors, network failures, timeouts
3. **Input Validation**: Invalid inputs, missing required fields
4. **Edge Cases**: Empty results, pagination, large datasets
5. **Context Cancellation**: Verify graceful handling of cancelled contexts

### Mocking
- Mock `client.TwentyClient` interface
- Mock HTTP responses for each API call
- Use `httptest.Server` for integration tests

### Assertions
- Verify correct API calls made
- Check returned data structure
- Validate error handling
- Confirm context propagation

Include benchmark tests for performance validation.
