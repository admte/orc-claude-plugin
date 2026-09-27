---
name: manage-orc8r
description: Use when the user asks about ORC8R Cloud organizations, projects, nodes, pools, billing, usage, or changes to those resources.
---

Use the ORC8R connector to work with resources the user can access.

1. For nodes and usage, use the dedicated read tools: `list_nodes` (every node the user can see, unfiltered), `get_node`, `read_node_logs`, and `get_org_usage`. For anything else, find the relevant API operation with `search_operations` and inspect its inputs with `describe_operation`.
2. Use `call_read_operation` for reads. Explain any missing organization, project, or other identifier you need before proceeding.
3. For a requested change, inspect the operation and its inputs before using `call_write_operation`. State the target and expected effect so the user can review the action. Do not perform a change the user has not authorized.
4. Report the actual result, including any permission or scope error. Do not claim a change succeeded from a proposed request alone.

The connection uses the user's ORC8R permissions and OAuth scopes. `orc:read` is always granted and allows reads. `orc:write` is required for changes and is chosen during ORC8R authorization.
