# Claude Desktop Configuration Guide

## Configuration File Location
Your Claude Desktop config should be at:
`~/.config/claude/claude_desktop_config.json`

## Current Working Configuration
Based on your existing filesystem MCP, your config likely looks like this:

```json
{
  "mcpServers": {
    "filesystem": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-filesystem", "/Users/przemyslawrudzki/Projects/claude-filesystem-mcp"],
      "env": {}
    }
  }
}
```

## Updated Configuration with SQLite
Add SQLite MCP to your existing config:

```json
{
  "mcpServers": {
    "filesystem": {
      "command": "npx", 
      "args": ["-y", "@modelcontextprotocol/server-filesystem", "/Users/przemyslawrudzki/Projects/claude-filesystem-mcp"],
      "env": {}
    },
    "sqlite": {
      "command": "npx",
      "args": ["-y", "mcp-server-sqlite-npx", "/Users/przemyslawrudzki/Projects/claude-filesystem-mcp/projects/mcp-learning/knowledge-base/mcp-knowledge.db"],
      "env": {}
    }
  }
}
```

## Setup Commands
Try these in order:

1. **Install the SQLite MCP server:**
   ```bash
   npm install -g mcp-server-sqlite-npx
   ```

2. **If that fails, try without global install:**
   The config uses `npx -y` which downloads on demand, so global install isn't required.

3. **Test the server directly:**
   ```bash
   npx -y mcp-server-sqlite-npx /Users/przemyslawrudzki/Projects/claude-filesystem-mcp/projects/mcp-learning/knowledge-base/mcp-knowledge.db
   ```

4. **Update your Claude Desktop config** with the JSON above

5. **Restart Claude Desktop**

## Next Steps
Once this is working, we'll:
1. Create your first database and tables
2. Test basic operations
3. Build your MCP learning tracking system
