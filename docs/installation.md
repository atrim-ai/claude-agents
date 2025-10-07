# Installation Guide

## Prerequisites

- [Claude Code](https://www.anthropic.com/claude-code) installed
- A project where you want to use these agents

## Installation Methods

### Method 1: Copy Individual Agents

Copy specific agents you need to your project's `.claude/agents/` directory:

```bash
# Create agents directory if it doesn't exist
mkdir -p /path/to/your/project/.claude/agents

# Copy specific agents
cp agents/testing-agent.md /path/to/your/project/.claude/agents/
cp agents/code-review-agent.md /path/to/your/project/.claude/agents/
```

### Method 2: Copy All Agents

Copy all agents to get the full suite:

```bash
# Clone this repository
git clone https://github.com/atrim-ai/claude-agents.git

# Copy all agents
cp claude-agents/agents/* /path/to/your/project/.claude/agents/
```

### Method 3: Symlink for Easy Updates

Create symlinks to keep agents updated:

```bash
# Clone this repository to a permanent location
git clone https://github.com/atrim-ai/claude-agents.git ~/claude-agents

# Create agents directory
mkdir -p /path/to/your/project/.claude/agents

# Create symlinks
ln -s ~/claude-agents/agents/* /path/to/your/project/.claude/agents/
```

## Verification

1. Start Claude Code in your project:
   ```bash
   cd /path/to/your/project
   claude-code
   ```

2. Test an agent:
   ```
   Use the testing-agent to validate infrastructure
   ```

3. You should see the agent execute and provide output

## Configuration

Agents can be customized by editing the markdown files:

```bash
# Edit an agent's behavior
nano /path/to/your/project/.claude/agents/testing-agent.md
```

### Key Customization Points

- **tools**: Which Claude Code tools the agent can use
- **model**: Which Claude model to use (e.g., `claude-3-opus-4-20250805`)
- **description**: Short description shown in agent list
- **Prompt content**: The full agent instructions and behavior

## Troubleshooting

### Agent Not Found

If Claude Code doesn't recognize an agent:

1. Verify the file is in `.claude/agents/` directory
2. Check the file has `.md` extension
3. Verify the YAML frontmatter is valid:
   ```yaml
   ---
   name: agent-name
   description: Agent description
   tools: ["*"]
   ---
   ```

### Agent Not Working as Expected

1. Read the agent's documentation in the markdown file
2. Check the agent's tool requirements
3. Ensure your project structure matches agent expectations
4. Review agent-specific prerequisites in the file

## Next Steps

- See [README.md](../README.md) for agent descriptions and usage examples
- Review [contribution.md](contribution.md) for customization guidelines
- Check individual agent files for specific requirements

## Uninstallation

Remove agents you no longer need:

```bash
rm /path/to/your/project/.claude/agents/agent-name.md
```

Or remove all agents:

```bash
rm -rf /path/to/your/project/.claude/agents/*
```
