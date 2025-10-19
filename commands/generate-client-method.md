<!-- fake-claude-plugins/commands/generate-client-method.md -->
---
description: Generate a Twenty CRM API client method
argument-hint: [method-name] [http-method]
---

@mcp-dev-go-sdk-agent Generate a client method in `internal/client/twenty_client.go`:

**Method Name**: `$1`
**HTTP Method**: `$2` (GET|POST|PUT|DELETE)

## Requirements

### Method Signature
```go
func (c *TwentyClient) $1(ctx context.Context, ...) (..., error)
```

### Implementation Must Include
- Context support for cancellation
- Proper HTTP method usage
- Request body marshaling (for POST/PUT)
- Response unmarshaling
- Error handling with wrapped errors
- Status code validation

### Pattern to Follow
Follow the same pattern as existing methods:
1. Marshal request body if needed
2. Create HTTP request with context
3. Set headers (Authorization, Content-Type)
4. Execute request
5. Check status code
6. Unmarshal response
7. Return typed result and error

Include usage example in doc comment.
```
