<div align="center">
  <img src="https://raw.githubusercontent.com/surri/wanderd/main/icons/icon.png" alt="wanderd" width="128" />
  <h1>wanderd</h1>
  <p><strong>Visual Entity-Relationship Diagram editor</strong></p>
  <p>Design database schemas visually. Import/export SQL. Connect with AI assistants via MCP.</p>

  <a href="https://marketplace.visualstudio.com/items?itemName=wanderd.wanderd"><img src="https://img.shields.io/visual-studio-marketplace/v/wanderd.wanderd" alt="VS Code Marketplace" /></a>
  <a href="https://open-vsx.org/extension/wanderd/wanderd"><img src="https://img.shields.io/open-vsx/v/wanderd/wanderd" alt="Open VSX" /></a>
  <a href="https://marketplace.visualstudio.com/items?itemName=wanderd.wanderd"><img src="https://img.shields.io/visual-studio-marketplace/i/wanderd.wanderd" alt="Installs" /></a>
</div>

---

![wanderd ERD Editor](https://raw.githubusercontent.com/surri/wanderd/main/images/hero.png)

## Features

### Visual ERD Canvas

Design your database schema on an interactive canvas. Drag and drop tables, zoom in and out, pan across large schemas, and use the minimap for quick navigation.

### SQL Import / Export

Import existing SQL DDL files to instantly generate visual diagrams. Export your designs back to SQL with full support for constraints, indexes, and default values.

### Multi-Dialect Support

Work with **PostgreSQL**, **MySQL**, and **SQLite**. Switch between dialects at any time — column types are automatically converted.

### Rich Table Editor

Edit tables with a powerful sidebar inspector. Set column types, toggle primary keys, nullable, and unique constraints, configure default values, and reorder columns by dragging.

### Relationship Management

Create foreign key relationships by dragging between columns. Configure cardinality (1:1, 1:n, n:m) and cascade rules (ON DELETE, ON UPDATE) with a visual editor.

### AI / MCP Integration

wanderd includes a built-in [Model Context Protocol](https://modelcontextprotocol.io) server. AI assistants can create, read, and modify your ERD diagrams programmatically — no manual setup required.

> **Example prompt:** *"Design an e-commerce database schema with users, orders, products, reviews, and payments"*
>
> The AI assistant calls wanderd's MCP tools to generate a complete `.wand` file with tables, columns, foreign keys, and canvas layout — all without leaving your editor.

## Installation

Search for **"wanderd"** in the Extensions panel (`Ctrl+Shift+X` / `Cmd+Shift+X`) and click **Install**.

Available on:
- [VS Code Marketplace](https://marketplace.visualstudio.com/items?itemName=wanderd.wanderd)
- [Open VSX Registry](https://open-vsx.org/extension/wanderd/wanderd) (Cursor, Kiro)

## Quick Start

1. Open the Command Palette (`Ctrl+Shift+P` / `Cmd+Shift+P`)
2. Run **"wanderd: New ERD"** to create a blank diagram
3. Add tables and start designing your schema

**Import an existing database:**

1. Run **"wanderd: Import SQL DDL"**
2. Select a `.sql` file
3. Your tables appear as a visual diagram with auto-layout

## Commands

| Command | Description |
|---------|-------------|
| `wanderd: New ERD` | Create a new empty ERD file |
| `wanderd: Import SQL DDL` | Import tables from a SQL file |
| `wanderd: Export to SQL DDL` | Export diagram as a SQL file |
| `wanderd: Copy SQL to Clipboard` | Copy DDL to clipboard |
| `wanderd: Change SQL Dialect` | Switch between PostgreSQL, MySQL, SQLite |

## Keyboard Shortcuts

| Shortcut | Action |
|----------|--------|
| `Ctrl/Cmd + Z` | Undo |
| `Ctrl/Cmd + Shift + Z` | Redo |
| `Ctrl/Cmd + C` | Copy SQL (selected table or full schema) |
| `Ctrl/Cmd + V` | Paste SQL to import |
| `Ctrl/Cmd + D` | Duplicate selected table |
| `Ctrl/Cmd + A` | Fit view |
| `Ctrl/Cmd + 0` | Reset zoom / fit view |
| `Ctrl/Cmd + =` | Zoom in |
| `Ctrl/Cmd + -` | Zoom out |
| `Ctrl/Cmd + B` | Toggle sidebar |
| `Delete / Backspace` | Delete selected table |
| `F2` | Rename selected table |
| `Tab / Shift+Tab` | Navigate between tables |
| `Arrow keys` | Move table (10px) |
| `Shift + Arrow keys` | Move table (50px) |
| `Escape` | Clear selection |

## SQL Dialect Support

| Feature | PostgreSQL | MySQL | SQLite |
|---------|-----------|-------|--------|
| Column types | Full (jsonb, uuid, timestamptz, serial) | Mapped (json, varchar, datetime, auto_increment) | Mapped (text, integer, blob) |
| Enums | `CREATE TYPE ... AS ENUM` | Inline `ENUM()` | Not supported |
| Auto-increment | `SERIAL` / `BIGSERIAL` | `AUTO_INCREMENT` | `AUTOINCREMENT` |
| Identifier quoting | `"double quotes"` | `` `backticks` `` | `"double quotes"` |

## MCP Server

wanderd's built-in MCP server lets AI assistants work with your ERD diagrams. It auto-registers with supported clients on extension activation.

**Supported AI clients:**
- Claude Code / Claude Desktop
- Cursor
- Kiro
- Gemini
- Codex

### Available Tools

| Tool | Description |
|------|-------------|
| `create_erd` | Create a new `.wand` file with a complete schema |
| `update_erd` | Replace the schema in an existing `.wand` file |
| `get_erd_state` | Read a `.wand` file and return its current schema |
| `list_erds` | Find all `.wand` files in a directory |
| `get_erd_guidelines` | Get ERD design best practices and conventions |

## File Format

wanderd uses `.wand` files — human-readable JSON that stores your schema definition including tables, columns, relationships, indexes, and canvas layout positions.

`.wand` files produce clean diffs and merge naturally, making them ideal for version control.

## Desktop App

wanderd is also available as a standalone desktop application.
Visit [wanderd releases](https://github.com/surri/wanderd/releases) for downloads.

## License

Copyright (c) 2026 wanderd. All rights reserved. See [LICENSE](LICENSE) for details.
