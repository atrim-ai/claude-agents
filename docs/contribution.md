# Contributing to Claude Agents

Thank you for your interest in contributing! This repository contains Claude Code agents that can be shared and improved by the community.

## How to Contribute

### 1. Improving Existing Agents

If you find ways to improve an existing agent:

1. **Fork the repository**
   ```bash
   # Click "Fork" on GitHub or:
   gh repo fork atrim-ai/claude-agents
   ```

2. **Make your improvements**
   - Edit the agent markdown file
   - Test the agent in your own project
   - Document your changes

3. **Submit a pull request**
   ```bash
   git checkout -b improve-testing-agent
   # Make your changes
   git add agents/testing-agent.md
   git commit -m "feat: Improve testing-agent error handling"
   git push origin improve-testing-agent
   gh pr create
   ```

### 2. Adding New Agents

To contribute a new agent:

1. **Create the agent file**
   ```bash
   # Use this template
   cat > agents/my-new-agent.md << 'AGENT'
   ---
   name: my-new-agent
   description: Brief description of what the agent does
   tools: ["*"]  # or list specific tools
   ---

   You are the my-new-agent for [purpose].

   ## Responsibilities

   1. [Responsibility 1]
   2. [Responsibility 2]

   ## Process

   [Detailed instructions for the agent...]
   AGENT
   ```

2. **Test thoroughly**
   - Use the agent in a real project
   - Verify it works as documented
   - Test edge cases

3. **Document well**
   - Clear description in frontmatter
   - Detailed responsibilities
   - Usage examples
   - Common pitfalls

4. **Submit for review**
   ```bash
   git add agents/my-new-agent.md
   git commit -m "feat: Add my-new-agent for [purpose]"
   git push
   gh pr create
   ```

### 3. Improving Documentation

Documentation improvements are always welcome:

- README.md - Main documentation
- docs/installation.md - Installation guide
- docs/contribution.md - This file
- Individual agent documentation

## Agent Design Guidelines

### Frontmatter Requirements

```yaml
---
name: agent-name  # kebab-case, unique identifier
description: Brief one-line description
tools: ["*"]  # Or specific tools: ["Read", "Write", "Grep"]
model: claude-3-opus-4-20250805  # Optional: specific model
---
```

### Content Structure

1. **Opening Statement**
   ```markdown
   You are the [agent-name] for [primary purpose].
   ```

2. **Responsibilities Section**
   - Numbered list of clear responsibilities
   - Specific, actionable items

3. **Process Section**
   - Step-by-step workflow
   - Decision trees for complex scenarios
   - Error handling guidance

4. **Examples** (optional but recommended)
   - Usage examples
   - Common patterns
   - Before/after comparisons

### Best Practices

**DO:**
- ✅ Use clear, direct language
- ✅ Provide specific examples
- ✅ Include error handling instructions
- ✅ Document prerequisites
- ✅ Explain "why" not just "what"
- ✅ Test with real projects
- ✅ Keep focus narrow and specific

**DON'T:**
- ❌ Create overly broad agents
- ❌ Use vague instructions
- ❌ Skip error scenarios
- ❌ Assume context without stating it
- ❌ Duplicate existing agent functionality
- ❌ Include sensitive information

## Testing Your Agent

Before submitting:

1. **Functional Testing**
   ```bash
   # Copy to a test project
   cp agents/my-agent.md ~/test-project/.claude/agents/
   
   # Start Claude Code
   cd ~/test-project
   claude-code
   
   # Test the agent
   # In Claude Code: "Use the my-agent to [task]"
   ```

2. **Validation Checklist**
   - [ ] Agent executes without errors
   - [ ] Produces expected results
   - [ ] Handles edge cases gracefully
   - [ ] Documentation is accurate
   - [ ] Examples work as shown
   - [ ] No hardcoded paths or secrets

3. **Peer Review**
   - Have someone else test the agent
   - Gather feedback on clarity
   - Iterate based on feedback

## Code of Conduct

- Be respectful and constructive
- Focus on improving the agents
- Help others learn and grow
- Give credit where it's due
- Follow the review process

## Questions or Issues?

- **Bug Reports**: Open an issue with detailed description
- **Feature Requests**: Open an issue explaining the use case
- **Questions**: Start a discussion on GitHub
- **Security**: Email security@atrim.ai (do not open public issues)

## License

By contributing, you agree that your contributions will be licensed under the MIT License.

## Recognition

Contributors will be recognized in:
- Git commit history
- Release notes
- README.md contributors section (for significant contributions)

Thank you for helping make Claude Agents better!
