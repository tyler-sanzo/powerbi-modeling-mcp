# CLAUDE.md - AI Assistant Guide for Power BI Modeling MCP Server

This document provides comprehensive guidance for AI assistants (like Claude) working with the Power BI Modeling MCP Server repository.

## Repository Overview

**Project Name:** Power BI Modeling MCP Server
**Type:** Documentation and distribution repository for an MCP (Model Context Protocol) server
**Primary Purpose:** Provides documentation, examples, and guides for the Power BI Modeling MCP Server
**Distribution:** The actual server is distributed as a compiled Windows executable (`powerbi-modeling-mcp.exe`) within a VS Code extension
**Current Version:** 0.1.9 (as of latest release)
**Status:** Public Preview
**Organization:** Microsoft (Analysis Services team)

### What This Repository Contains

This is primarily a **documentation repository**. It does NOT contain the source code for the MCP server itself. Instead, it contains:

- Comprehensive user documentation (README.md)
- Installation and setup guides
- Troubleshooting documentation
- Example scenarios and use cases
- Issue templates for community feedback
- Images and diagrams for documentation

### What This Repository Does NOT Contain

- TypeScript/JavaScript source code for the MCP server
- package.json or npm dependencies
- Build scripts or compilation tools
- Unit tests or test suites
- The actual MCP server implementation (distributed as compiled .exe)

## Project Purpose

The Power BI Modeling MCP Server implements the [MCP specification](https://modelcontextprotocol.io/introduction) to enable AI agents to interact with Power BI semantic models. It allows:

- **Natural language modeling operations** - Create, update, and manage tables, columns, measures, relationships
- **Bulk operations at scale** - Execute batch operations on hundreds of objects simultaneously
- **Best practices application** - Evaluate and implement modeling best practices
- **Agentic workflows** - Work with TMDL and Power BI Project files for autonomous modeling
- **DAX query execution** - Execute and validate DAX queries against semantic models

## Repository Structure

```
powerbi-modeling-mcp/
├── .github/
│   └── ISSUE_TEMPLATE/
│       ├── BUGREPORT.md          # Bug report template
│       └── FEATUREREQUEST.md     # Feature request template
├── docs/
│   └── img/                       # Documentation images and diagrams
│       ├── e2e-diagram.png        # End-to-end architecture diagram
│       ├── mcp-server-elicitation.png
│       ├── troubleshooting-vscode-output.png
│       ├── vscode-extension-install.png
│       ├── vscode-mcp-prompts.png
│       ├── vscode-mcp-settings.png
│       └── vscode-mcp-tools.png
├── CHANGELOG.md                   # Version history and release notes
├── CLAUDE.md                      # This file - AI assistant guide
├── CODE_OF_CONDUCT.md            # Microsoft Open Source Code of Conduct
├── LICENSE                        # MIT License
├── README.md                      # Main documentation
├── SECURITY.md                    # Security reporting guidelines
├── SUPPORT.md                     # Support information
└── TROUBLESHOOTING.md            # Troubleshooting guide
```

## Key Documentation Files

### README.md
The primary documentation file. Contains:
- Feature overview and capabilities
- Installation instructions (VS Code extension and manual)
- Getting started guide with connection examples
- Complete tool catalog (25+ MCP tools)
- Available prompts and resources
- Settings and configuration options
- Security, compliance, and legal considerations

### TROUBLESHOOTING.md
Diagnostic and resolution guide covering:
- MCP server logging and output inspection
- EventSource trace collection with dotnet-trace
- Server restart procedures
- Binary location information
- FAQs for common issues

### CHANGELOG.md
Version history tracking:
- Feature additions
- Bug fixes
- Breaking changes
- Platform support updates

## MCP Server Capabilities

The server provides 25+ MCP tools organized into categories:

### Core Operations
- `connection_operations` - Connect to Power BI Desktop or Fabric
- `database_operations` - Manage semantic models and TMDL import/export
- `transaction_operations` - Control database transactions

### Model Objects
- `table_operations` - Manage tables
- `column_operations` - Manage columns
- `measure_operations` - Manage DAX measures
- `relationship_operations` - Handle table relationships
- `partition_operations` - Manage table partitions
- `user_hierarchy_operations` - Work with hierarchies
- `calculation_group_operations` - Manage calculation groups
- `function_operations` - Manage DAX user-defined functions

### Query & Analysis
- `dax_query_operations` - Execute and validate DAX queries
- `trace_operations` - Capture Analysis Services events

### Globalization
- `culture_operations` - Manage cultures for multi-language support
- `object_translation_operations` - Handle object translations

### Security & Views
- `security_role_operations` - Configure RLS and security roles
- `perspective_operations` - Manage perspectives

### Bulk Operations
- `batch_table_operations` - Bulk table operations
- `batch_column_operations` - Bulk column operations
- `batch_measure_operations` - Bulk measure operations
- `batch_function_operations` - Bulk function operations
- `batch_perspective_operations` - Bulk perspective management
- `batch_object_translation_operations` - Bulk translations

### Other
- `named_expression_operations` - Power Query parameters
- `calendar_operations` - Calendar and time intelligence
- `query_group_operations` - Power Query expression groups

## Built-in Prompts

The MCP server includes pre-configured prompts:

- `CreateDAXQuery` - Generate DAX from natural language
- `RunDAXQueryWithMetrics` - Execute with performance metrics
- `AnalyzeDAXQuery` - Performance analysis with cache clearing
- `ConnectToPowerBIDesktop` - Connect to local Power BI Desktop
- `ConnectToFabric` - Connect to Fabric workspace
- `ConnectToPBIP` - Load from Power BI Project files

## Development Workflows

### Documentation Updates

When updating documentation:

1. **README.md changes** - Primary user-facing documentation
   - Keep the tool catalog in sync with actual MCP server capabilities
   - Update version numbers when referencing specific releases
   - Maintain consistent formatting and structure
   - Ensure all example prompts are realistic and tested

2. **TROUBLESHOOTING.md changes** - Diagnostic guides
   - Add new issues as they're reported and resolved
   - Keep VS Code paths and UI references current
   - Update dotnet-trace commands if .NET versions change

3. **CHANGELOG.md updates** - Version tracking
   - Add entries for each release
   - Follow existing format (version header, bullet points)
   - Group changes by type (features, bug fixes, breaking changes)

4. **Image updates** - Screenshots and diagrams
   - Place in `docs/img/` directory
   - Use descriptive, kebab-case filenames
   - Reference from markdown files using relative paths
   - Keep screenshots current with UI changes

### Issue Management

When working with GitHub issues:

1. **Bug reports** follow `.github/ISSUE_TEMPLATE/BUGREPORT.md`
   - Require: Version, LLM model used, description, expected vs actual behavior
   - Look for additional context (chat exports, screenshots, logs)

2. **Feature requests** follow `.github/ISSUE_TEMPLATE/FEATUREREQUEST.md`
   - Require: Description, use case, additional context
   - Consider MCP specification constraints
   - Consider Power BI/Analysis Services limitations

### Git Workflow

This repository follows standard GitHub flow:

- **Main branch:** Protected, contains stable documentation
- **Feature branches:** Use descriptive names (e.g., `claude/add-claude-documentation-0iGN2`)
- **Commits:** Clear, descriptive commit messages
- **Pull requests:** Required for merging to main

## Key Conventions

### Documentation Style

- **Tone:** Professional, clear, concise
- **Formatting:** GitHub-flavored Markdown
- **Code blocks:** Use appropriate language tags (```json, ```powershell, etc.)
- **Emphasis:** Use **bold** for UI elements, *italic* for emphasis
- **Lists:** Use `-` for unordered lists, numbers for sequential steps
- **Emojis:** Used sparingly in headings for visual hierarchy (✨, 💡, 📦, 🚀, etc.)

### Terminology

**Consistent terms to use:**
- "Semantic model" (not "dataset" - Power BI terminology update)
- "MCP server" (not "server" alone - be specific)
- "Power BI Desktop" (proper capitalization)
- "Fabric workspace" (not "workspace" alone)
- "TMDL" (Tabular Model Definition Language)
- "PBIP" (Power BI Project)
- "DAX" (Data Analysis Expressions)
- "Analysis Services"

**Avoid:**
- "Dataset" (deprecated Power BI term)
- Overly technical jargon without explanation
- Assuming knowledge of Power BI internals

### File Naming

- Markdown files: UPPERCASE.md (README.md, CHANGELOG.md, etc.)
- Images: lowercase-with-hyphens.png
- Directories: lowercase

## Important Context for AI Assistants

### What AI Assistants Should Know

1. **This is a documentation repo** - Don't try to find or modify TypeScript/JavaScript source code

2. **Public Preview status** - Features and APIs may change significantly before GA

3. **Windows-only MCP server** - The compiled server runs on Windows (x64 and ARM64)

4. **VS Code is primary distribution** - Most users install via VS Code extension

5. **Security and compliance are critical** - This connects to production Power BI data

6. **LLM quality matters** - Documentation emphasizes using GPT-5 or Claude Sonnet 4.5

7. **MCP specification compliance** - Server implements MCP elicitation protocol for confirmations

8. **External Tools integration** - Follows same rules as Power BI External Tools

### Common User Scenarios

Users interact with this MCP server to:
- Bulk rename objects following naming conventions
- Add descriptions/documentation to semantic models
- Translate models to multiple languages
- Refactor DAX calculations into calculation groups
- Create parameters for data source switching
- Benchmark DAX performance
- Generate model documentation

### Safety and Confirmations

The MCP server implements safety features:
- **Elicitation prompts** before first model modification
- **Elicitation prompts** before first query execution
- **Transaction support** for rollback capability
- **Read-only mode** available via `--readonly` flag
- **Backup recommendations** prominently featured in warnings

### Security Considerations

Documentation must emphasize:
- Use of Azure Identity SDK for authentication (never storing tokens)
- Compliance responsibility for third-party integrations
- Least-privilege RBAC recommendations
- Entra ID authentication requirements
- Network isolation guidance
- Export control compliance

### Known Limitations

Document and respect these limitations:
- Fabric workspace connections subject to tenant rollout
- Follows External Tools rules and behaviors
- Cannot modify report pages or diagram layouts
- Requires appropriate Fabric RBAC permissions
- May not be supported by all MCP clients

## Working with This Repository

### When Asked to Make Changes

If asked to modify documentation:

1. **Read the relevant file first** - Always use the Read tool before editing
2. **Maintain consistency** - Follow existing formatting and terminology
3. **Update related files** - If changing README examples, consider TROUBLESHOOTING impact
4. **Keep it accurate** - Don't document features that don't exist in the server
5. **Consider the audience** - Target is Power BI developers and AI application builders

### When Asked Questions

If asked about the Power BI Modeling MCP Server:

1. **Cite documentation** - Reference specific sections (e.g., README.md:125-156)
2. **Distinguish repo vs server** - Clarify when answering about the docs vs the compiled server
3. **Check version context** - CHANGELOG.md shows what's available in which version
4. **Consider Public Preview status** - Features may change

### When Creating Content

If creating new documentation:

1. **Follow existing structure** - Look at README.md for formatting patterns
2. **Include warnings** - Especially for destructive operations or security concerns
3. **Provide examples** - Users need concrete, copy-pasteable examples
4. **Link to official docs** - Reference Microsoft Learn documentation where appropriate

## Useful External References

- **MCP Specification:** https://modelcontextprotocol.io/introduction
- **Power BI Projects/TMDL:** https://learn.microsoft.com/power-bi/developer/projects/projects-dataset#tmdl-format
- **External Tools:** https://learn.microsoft.com/power-bi/transform-model/desktop-external-tools
- **Azure Identity SDK:** https://github.com/Azure/azure-sdk-for-net/blob/main/sdk/identity/Azure.Identity/README.md
- **Microsoft Security for MCP:** https://learn.microsoft.com/en-us/azure/api-management/secure-mcp-servers
- **Privacy Statement:** https://www.microsoft.com/privacy/privacystatement
- **Code of Conduct:** https://opensource.microsoft.com/codeofconduct/

## Quick Reference

### Most Important Files to Know
- `README.md` - Primary documentation (24KB+)
- `TROUBLESHOOTING.md` - User support
- `CHANGELOG.md` - Version history

### Most Common Tasks
1. Update README with new features/examples
2. Add troubleshooting entries
3. Update CHANGELOG for releases
4. Refresh screenshots when UI changes
5. Respond to GitHub issues

### Things to Never Do
- Don't create fake TypeScript/JavaScript source code
- Don't claim the repository contains server source code
- Don't recommend unsupported platforms (macOS, Linux)
- Don't suggest bypassing security confirmations without explicit user request
- Don't add unnecessary dependencies or build tools

### Things to Always Do
- Emphasize backup requirements before modeling changes
- Include security and compliance warnings
- Reference official Microsoft documentation
- Maintain Public Preview disclaimers
- Keep terminology consistent with Power BI standards

## Recent Changes (v0.1.9)

Latest version includes:
- Bug fixes for connection naming and null references
- Support for ARM-based processors
- Improved stability for table operations

## Version History Highlights

- **0.1.9** - ARM support, bug fixes
- **0.1.8** - Documentation updates
- **0.1.7** - Automatic connection names, execution metrics
- **0.1.5** - Trace operation optimization, query confirmation
- **0.1.1** - MCP prompts, Direct Lake support, trace operations
- **0.1.0** - Initial public preview release

---

**Last Updated:** 2025-12-18
**Repository:** https://github.com/microsoft/powerbi-modeling-mcp
**License:** MIT
**Maintainer:** Microsoft Analysis Services Team
