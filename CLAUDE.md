# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Purpose

This is a **prompt engineering utilities repository** containing reusable prompts, structured patterns, documentation templates, and custom Claude Code commands. It focuses on:

- Structured prompts for generating technical documentation (PRDs, HLDs, FDDs)
- Interview-style prompts that guide users through information gathering
- Multi-agent frameworks for complex tasks (Systems Auditor)
- Diagram generation workflows (C4 and Mermaid diagrams from FDDs)
- Example documents demonstrating best practices

**Key principle**: This is a documentation and prompt repository, NOT a code project. There is no build system, test suite, or application to run.

## Repository Structure

```
.
├── .claude/
│   ├── agents/              # Custom agent definitions (c4-diagram-generator)
│   └── commands/            # Slash commands (/commit, /update-readme, /generate-c4)
├── prompts/                 # Reusable prompt templates organized by category
│   ├── PRD de Feature/
│   ├── Design e Arquitetura/High Level Document (HLD)/
│   ├── Feature Design Document (FDD)/
│   ├── Deep Research/
│   ├── Diagramas C4/        # C4 diagram generation prompts
│   ├── Diagramas Mermaid/   # Mermaid diagram generation prompts
│   └── Systems Auditor/     # Multi-agent auditing framework
└── Exemple/                 # Example documents demonstrating prompt outputs
    └── docs/
        ├── prd/             # Example PRDs
        ├── Design e Arquitetura/High Level Document (HLD)/
        ├── Feature Design Document (FDD)/
        ├── Deep Research/
        ├── Diagramas C4/
        └── Diagramas Mermaid/
```

## Custom Commands

### `/commit`

Creates conventional commits following the Conventional Commits specification.

**Usage**: `/commit`

**Behavior**:
- Analyzes `git status` and `git diff` to understand changes
- Determines appropriate commit type (feat, fix, docs, style, refactor, perf, test, build, ci, chore, revert)
- Generates commit message in imperative mood with optional body
- **IMPORTANT**: Does NOT include AI/Claude metadata or Co-Authored-By tags
- Stages relevant files and creates the commit

### `/update-readme`

Automatically updates the [README.md](README.md) by scanning prompt files, examples, and commands.

**Usage**: `/update-readme`

**Behavior**:
- Scans `prompts/`, `Exemple/`, and `.claude/commands/` directories
- Extracts descriptions from file content
- Organizes into categories with relative links
- Maintains alphabetical order within categories
- Preserves custom sections in existing README

### `/generate-c4`

Generates C4 architecture diagrams from Feature Design Documents.

**Usage**: `/generate-c4 <fdd-path> [output-folder] [--no-images]`

**Examples**:
- `/generate-c4 docs/feature-design.md`
- `/generate-c4 docs/feature-design.md docs/diagrams`
- `/generate-c4 docs/feature-design.md docs/diagrams --no-images`

**Behavior**:
- Invokes the `c4-diagram-generator` agent via Task tool
- Generates separate `.puml` files for each C4 level (System Context, Container, Component, Code)
- Creates analysis `.md` file
- Optionally generates PNG images (default: enabled, disable with `--no-images`)
- **Language matching**: Diagrams use the same language as the FDD (Portuguese/English)
- **Technical terms**: Keeps technology names in English regardless of FDD language

## Custom Agents

### c4-diagram-generator

Specialized agent for generating C4 architecture diagrams from FDDs.

**Location**: [.claude/agents/c4-diagram-generator.md](.claude/agents/c4-diagram-generator.md)

**Key capabilities**:
- Reads and analyzes Feature Design Documents
- Generates PlantUML C4 diagrams at multiple abstraction levels
- Automatically detects FDD language and generates diagrams in the same language
- Maintains proper orthography (accents, special characters) for Portuguese content
- Keeps technical terms (Redis, Kafka, API, etc.) in English
- Creates separate `.puml` files for each diagram type
- Optionally generates PNG images with error correction

**When it's invoked**: Automatically used by `/generate-c4` command

## Working with Prompts

### Prompt Categories

1. **Interview-style prompts**: Guide users through structured questions to gather requirements
   - PRD de Feature, HLD, FDD prompts
   - Conduct adaptive conversations with focused questions
   - Generate structured output after gathering context

2. **Agent-based prompts**: Define specialized agents for complex tasks
   - Systems Auditor (orchestrator, dependency-auditor, architectural-analyzer, component-deep-analyzer)
   - C4 and Mermaid diagram generators
   - Designed to work within Claude Code's Task tool

3. **Command prompts**: Define slash command behavior
   - Live in `.claude/commands/`
   - Follow format with frontmatter description
   - May invoke agents or perform direct actions

### Adding New Prompts

When adding new prompts to `prompts/`:

1. Use descriptive filenames with underscores: `Entrevista_para_geracao_de_um_HLD.md`
2. Include clear purpose/objective at the top of the file
3. Structure with clear sections and instructions
4. Place in appropriate category folder
5. Run `/update-readme` to add it to the README automatically

### Adding New Examples

When adding examples to `Exemple/docs/`:

1. Match the structure of existing examples
2. Use the same category folders as `prompts/`
3. Demonstrate the full output of corresponding prompts
4. Include realistic, detailed content (like the Rate Limiter examples)

## Language Conventions

This repository is **bilingual** (Portuguese and English):

- **README.md**: Portuguese (primary language for repository navigation)
- **Prompts**: Primarily Portuguese with technical terms in English
- **Examples**: Match the language patterns of real-world usage
- **Code/Commands**: English variable names, Portuguese descriptions where appropriate

When generating diagrams or technical content:
- **Detect the source document language** first
- **Match the language** in generated content
- **Keep technical terms** (API, Service, Container, Redis, etc.) in English
- **Use proper orthography**: Include accents and special characters (Serviço, Autenticação, Configuração)

## Multi-Agent Workflows

### Systems Auditor Framework

A coordinated multi-agent system for comprehensive project auditing.

**Agents**:
- `orchestrator`: Maintains MANIFEST.md, manages directory structure, coordinates workflow
- `dependency-auditor`: Analyzes dependencies, versions, vulnerabilities
- `architectural-analyzer`: Documents architectural patterns, components, data flows
- `component-deep-analyzer`: Deep-dives into individual components

**Usage**: Invoke via `/run-project-state-full-report` command (when available)

**Key principle**: The orchestrator manages the workflow under Claude Code coordination. It does not invoke sub-agents directly; Claude Code orchestrates all agent invocations.

## Git Workflow

### Branching
- Main branch: `master`
- Work directly on master for documentation updates
- Create feature branches for significant new prompt templates or frameworks

### Commit Messages
- Always use `/commit` command for consistent conventional commits
- Types commonly used: `feat`, `docs`, `chore`
- Scope examples: `(docs)`, `(prompts)`, `(claude-code)`, `(examples)`

### Recent Commit Patterns
```
feat(docs): add systems auditor multi-agent framework
feat(docs): add mermaid diagrams prompts and examples
feat(claude-code): add c4-diagram-generator agent
feat(docs): add deep research and c4 diagrams prompts with examples
```

## Common Workflows

### Updating Documentation After Adding New Prompts

1. Add prompt files to appropriate `prompts/` subdirectory
2. Add corresponding examples to `Exemple/docs/` if applicable
3. Run `/update-readme` to regenerate README links
4. Review README changes
5. Run `/commit` to create conventional commit

### Generating Diagrams from FDDs

1. Ensure FDD exists and is complete
2. Run `/generate-c4 path/to/fdd.md [output-folder]`
3. Agent will generate `.puml` files and analysis
4. PNG images generated by default (use `--no-images` to skip)
5. Review generated diagrams for accuracy

### Creating New Custom Agents

1. Create agent definition in `.claude/agents/[agent-name].md`
2. Include frontmatter with `name`, `description`, `model`, `color`
3. Write detailed instructions for agent behavior
4. Create corresponding command in `.claude/commands/` to invoke the agent
5. Test with Task tool: `subagent_type="agent-name"`
6. Document in README via `/update-readme`

## File Naming Conventions

- **Prompts**: Use underscores for spaces: `Entrevista_para_geracao_de_um_HLD.md`
- **Examples**: Use spaces in folder names: `Design e Arquitetura/High Level Document (HLD)/`
- **Commands**: Use lowercase with hyphens: `generate-c4.md`, `update-readme.md`
- **Agents**: Use lowercase with hyphens: `c4-diagram-generator.md`

## Important Notes

- **No build/test commands**: This is a documentation repository with no code to build or test
- **Focus on prompt quality**: Prompts should be clear, structured, and produce consistent results
- **Examples are critical**: Well-crafted examples demonstrate prompt effectiveness
- **Agent coordination**: When using multi-agent frameworks, Claude Code orchestrates; agents don't invoke each other
- **Language sensitivity**: Always respect the language of source documents when generating content
