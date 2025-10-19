<!-- fake-claude-plugins/commands/test-mcp-server.md -->
---
description: Generate curl commands to test MCP server endpoints
---

@mcp-dev-go-sdk-agent Generate complete curl test suite for the MCP server:

## Test Commands Required

1. **Server Initialization**
   - Initialize connection
   - Verify protocol version

2. **List All Tools**
   - tools/list request
   - Verify all expected tools present

3. **Test Each Category**
   - People: create_person, list_people
   - Companies: create_company, list_companies
   - Tasks: create_task, list_tasks
   - Notes: create_note, list_notes
   - Metadata: get_metadata_objects
   - Search: search_records

Use **localhost:8080** and proper **JSON-RPC 2.0** format with request IDs.

Include expected responses for each test.
