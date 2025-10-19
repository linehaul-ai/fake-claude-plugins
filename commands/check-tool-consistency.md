<!-- fake-claude-plugins/commands/check-tool-consistency.md -->
---
description: Verify all entity tools follow the same patterns and conventions
---

@mcp-dev-go-sdk-agent Compare all tool files in `internal/tools/` directory:

## Consistency Checks

### Naming Conventions
- Tool names: `create_entity`, `get_entity`, `update_entity`, `list_entity`, `delete_entity`
- Input structs: `CreateEntityInput`, `ListEntityInput`, etc.
- Registration functions: `RegisterEntityTools(server, client)`

### CRUD Completeness
- All entities have full CRUD operations
- List operations support: limit, offset, search/filter
- Get operations handle not-found errors
- Update supports partial updates
- Delete returns appropriate messages

### Error Handling Patterns
- Consistent error wrapping: `fmt.Errorf("operation failed: %w", err)`
- Same HTTP status code handling
- Uniform error messages to clients

### Jsonschema Tags
- All required fields marked with `required`
- Email fields have `format=email`
- Descriptions present for all fields
- Consistent validation patterns

**Report any inconsistencies and suggest standardization.**
