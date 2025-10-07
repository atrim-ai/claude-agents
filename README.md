# Claude Agents

Specialized Claude Code agents for software development workflows - AI-native development automation.

## Overview

This repository contains a collection of battle-tested Claude Code agents designed to streamline software development workflows. These agents enable AI-native development practices by automating routine tasks, enforcing quality standards, and maintaining consistency across your codebase.

## What are Claude Code Agents?

Claude Code agents are specialized AI assistants that run within the Claude Code environment. Each agent is designed for a specific task (testing, code review, documentation, etc.) and comes with:

- **Focused expertise** in a particular domain
- **Pre-defined tools** and capabilities
- **Structured workflows** for consistent results
- **Integration patterns** for working together

## Agent Catalog

### 🧪 Quality Assurance

#### testing-agent
**Comprehensive test execution and validation**

Validates infrastructure dependencies, executes test suites (unit, integration, e2e), runs code quality checks (lint, typecheck, build), analyzes test coverage, and provides detailed failure analysis with actionable fixes.

**Key Features:**
- Test structure validation (enforces `test/` subdirectories)
- Infrastructure health verification
- Comprehensive test suite execution
- Coverage analysis and gap identification

#### code-review-agent
**Quality assurance and best practices validation**

Reviews code changes for project convention adherence, checks for security issues, validates OpenTelemetry semantic conventions, ensures code hygiene, reviews documentation completeness, and suggests performance optimizations.

**Key Features:**
- Effect-TS pattern compliance validation
- Architectural boundary enforcement
- Detection commands for anti-patterns
- CI/CD integration support
- Dual mode: comprehensive local reviews or silent CI scanning

#### ui-review-agent
**Automated UI testing with console and screenshot capture**

Executes e2e tests with full instrumentation, collects diagnostic data (console logs, screenshots, page errors), analyzes visual issues from screenshots, correlates console errors with code issues, and generates comprehensive markdown reports.

**Key Features:**
- Browser console capture
- Automatic screenshot capture at key points
- Visual alignment debugging tool
- Performance observation tracking
- Accessibility concern identification

### 📦 Code Management

#### refactoring-specialist
**Expert refactoring with safety guarantees**

Specializes in safe code transformation, code smell detection, design pattern application, and systematic refactoring while preserving behavior.

**Key Features:**
- Code smell detection (long methods, large classes, etc.)
- Comprehensive refactoring catalog
- Automated AST transformations
- Test-driven refactoring approach
- Performance refactoring strategies

#### dryness-agent
**DRY violations and code duplication analysis**

Systematically analyzes codebase for code duplication, structural similarity, pattern duplication, and abstraction opportunities using ast-grep, semgrep, and jsinspect.

**Key Features:**
- Exact duplication detection
- Structural similarity analysis
- Effect-TS specific pattern detection
- DRYness score calculation
- CI/CD integration support

#### effect-ts-optimization-agent
**Effect-TS pattern optimization and validation**

Systematically analyzes and optimizes Effect-TS patterns, eliminates "as any" usage, ensures comprehensive validation (TypeScript, ESLint, tests) before declaring success.

**Key Features:**
- Test helper anti-pattern detection
- Effect pattern simplification
- Mock service typing improvements
- Type assertion elimination
- Effect.gen refactoring strategies

### 📝 Documentation & Planning

#### code-implementation-planning-agent
**Comprehensive implementation plans and design documents**

Generates detailed design documents and implementation plans for Effect-TS features without writing code. Creates structured plans that can be executed by other agents or developers.

**Key Features:**
- Design document generation following established templates
- Effect-TS service architecture planning
- Testing strategy specification
- Session recovery checkpoints
- Phase-based implementation breakdown

#### code-to-docs-sync-agent
**Bidirectional documentation synchronization**

Synchronizes package CLAUDE.md files with implementation code, validates test structure compliance, updates API contracts, and ensures mandatory conventions are followed.

**Key Features:**
- CLAUDE.md ↔ code synchronization
- API contract validation
- Test structure enforcement
- Error type consistency checking
- Missing implementation detection

#### blog-writing-agent
**Professional technical blog writer**

Creates clear, informative blog posts with measured tone and focus on implementation details. Avoids hyperbole and marketing language.

**Key Features:**
- AI writing tell avoidance
- Code example verification
- Dev.to metadata compliance
- Technical fact-checking
- Screenshot integration

### 🔄 Workflow Automation

#### pr-creation-agent
**PR creation with screenshot organization**

Organizes screenshots from staging into proper package documentation, updates documentation to reflect code changes, generates comprehensive PR descriptions, and prepares blog entry content.

**Key Features:**
- Date-based screenshot organization
- PR number verification workflow
- GitHub raw URL formatting
- Visual evidence integration
- Comprehensive PR structure templates

#### visual-content-agent
**Screenshot integration and visual branding**

Automates screenshot integration, generates blog cover images with consistent branding, creates PR visual documentation, and maintains visual branding standards.

**Key Features:**
- Screenshot organization automation
- Blog cover image generation
- README visual enhancement
- Architecture diagram creation
- Consistent design system application

#### claude-review-session-agent
**Historical context recovery and development continuity**

Reviews git commits, PRs, and Claude Code session logs to provide comprehensive insights for blog posts, daily notes, and development continuity.

**Key Features:**
- Git history analysis
- PR review and synthesis
- Session log recovery
- Context gap identification
- Development continuity support

## Installation

### Prerequisites

- [Claude Code](https://www.anthropic.com/claude-code) installed
- A codebase you want to apply these agents to

### Basic Setup

1. **Copy agents to your project:**

```bash
# Clone this repository
git clone https://github.com/atrim-ai/claude-agents.git

# Copy agents to your project's .claude/agents directory
mkdir -p /path/to/your/project/.claude/agents
cp claude-agents/agents/* /path/to/your/project/.claude/agents/
```

2. **Start using agents in Claude Code:**

```bash
cd /path/to/your/project
claude-code
```

3. **Invoke an agent:**

```
Use the testing-agent to run comprehensive tests
```

### Advanced Setup

For project-specific customization, you can modify the agent files in your `.claude/agents/` directory. Each agent is a markdown file with YAML frontmatter defining its capabilities and behavior.

## Usage Examples

### Running Tests

```
Use the testing-agent to validate infrastructure and execute the test suite
```

### Code Review Before Commit

```
Use the code-review-agent to review recent changes for quality and conventions
```

### Refactoring Code

```
Use the refactoring-specialist to analyze and refactor the authentication module
```

### Creating a Pull Request

```
Use the pr-creation-agent to organize screenshots and create a comprehensive PR
```

### Analyzing Code Duplication

```
Use the dryness-agent to scan for code duplication and suggest refactoring opportunities
```

### UI Testing with Diagnostics

```
Use the ui-review-agent to run e2e tests and analyze UI issues
```

## Agent Workflows

Agents can work together in orchestrated workflows:

### Daily Development Workflow

1. **Feature implementation** → manual development or `code-implementation-planning-agent`
2. **Periodic validation** → `testing-agent`
3. **Pre-commit review** → `code-review-agent`
4. **Documentation sync** → `code-to-docs-sync-agent`
5. **PR creation** → `pr-creation-agent` (after `pnpm typecheck:all` and `pnpm lint`)

### Quality Assurance Workflow

1. `testing-agent` → comprehensive test validation
2. `ui-review-agent` → UI testing with diagnostic capture (for UI changes)
3. `code-review-agent` → quality and convention check
4. `code-to-docs-sync-agent` → documentation alignment
5. Ready for commit/PR

### Refactoring Workflow

1. `dryness-agent` → identify duplication and refactoring opportunities
2. `refactoring-specialist` → apply safe transformations
3. `testing-agent` → verify behavior preservation
4. `code-review-agent` → validate improvements

## Customization

Each agent can be customized for your project's specific needs by editing the markdown files in `.claude/agents/`. Key customization points:

- **Tools**: Specify which Claude Code tools the agent can use
- **Model**: Specify which Claude model to use (e.g., `claude-3-opus-4-20250805`)
- **Behavior**: Modify the agent's instructions and workflow
- **Integration**: Add project-specific commands and validation

## Best Practices

1. **Use agents proactively**: Don't wait for problems - agents can prevent issues
2. **Combine agents**: Orchestrate multiple agents for complex workflows
3. **Customize for your stack**: Adapt agents to your technology choices
4. **Maintain consistency**: Use agents regularly to maintain code quality
5. **Trust but verify**: Agents are powerful but review their outputs

## Contributing

We welcome contributions! See [CONTRIBUTING.md](docs/contribution.md) for guidelines.

## License

MIT License - see [LICENSE](LICENSE) for details.

## Links

- [Claude Code Documentation](https://docs.anthropic.com/claude/docs/claude-code)
- [Example Project Using These Agents](https://github.com/clayroach/otel-ai)
- [Report Issues](https://github.com/atrim-ai/claude-agents/issues)

## Credits

These agents were developed as part of the [otel-ai project](https://github.com/clayroach/otel-ai), a 30-day AI-native observability platform challenge.

---

**Built with Claude Code** - AI-native development automation