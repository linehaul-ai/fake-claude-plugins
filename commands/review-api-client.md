<!-- fake-claude-plugins/commands/review-api-client.md -->
---
description: Review Twenty CRM API client for best practices
---

@mcp-dev-go-sdk-agent Review `internal/client/twenty_client.go`:

## Review Areas

### HTTP Client Usage
- Connection pooling configured
- Timeout settings appropriate
- Retry logic for transient failures
- Proper header management

### Error Handling
- HTTP status code handling comprehensive
- Network errors handled gracefully
- Context cancellation respected
- Error messages actionable

### Request/Response Handling
- Request body marshaling correct
- Response unmarshaling with error checks
- Empty response handling
- Large response streaming if needed

### Authentication
- API key properly secured (from env var)
- Bearer token format correct
- No credentials in logs

### Code Quality
- Methods follow consistent pattern
- DRY principle applied
- Proper documentation
- Thread-safe operations

Provide specific recommendations for improvements with code examples.
