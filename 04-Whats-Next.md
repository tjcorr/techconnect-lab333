# What's Next: Your Copilot Journey Continues

## 🎉 Congratulations!

You've completed the GitHub Copilot workshop! You've experienced firsthand how AI can transform your development workflow-from inline code suggestions to autonomous coding agents.

But this is just the beginning. GitHub Copilot is evolving rapidly, with new capabilities shipping regularly. To truly master Copilot and maximize its potential, there's a rich ecosystem of advanced features waiting for you to explore.

---

## 🚀 Advanced Topics to Explore


### Custom Instructions

Tailor Copilot's behavior to match your team's coding standards, architectural patterns, and preferences.

- **Repository instructions** - Add a **.github/copilot-instructions.md** file to give Copilot context about your project
- **Code review instructions** - Customize how Copilot reviews your PRs
- **Organization-wide standards** - Set consistent guidelines across all your repositories

Your repository already has custom instructions set up! Take a look at **.github/copilot-instructions.md** for the overall project-level instructions, and notice the individual instruction files in **.github/instructions/** for specific areas of the codebase (e.g., **api**, **database**, **frontend**). This layered approach lets you give Copilot targeted guidance for different parts of your project. Try opening the files to see an example of how to provide specific guidance to Copilot about our project!

> 📖 **Further Reading:** [Adding custom instructions for GitHub Copilot](https://docs.github.com/copilot/customizing-copilot/adding-repository-custom-instructions-for-github-copilot)

---

### Custom Agents

Create specialized versions of Copilot Coding Agent tailored to your unique workflows and coding conventions.

- **Tailored teammates** - Define agents that follow your standards, use the right tools, and implement team-specific practices
- **Agent profiles** - Simple Markdown files with YAML frontmatter that specify prompts, tools, and MCP servers
- **Multiple scopes** - Create repository-level agents (**.github/agents/**) or organization/enterprise-wide agents
- **Use anywhere** - Custom agents work on GitHub.com, VS Code, JetBrains, CLI, and more

**Example agent profile** (**.github/agents/readme-creator.md**):
```
---
name: readme-creator
description: Agent specializing in creating and improving README files
---

You are a documentation specialist focused on README files...
```

> 📖 **Further Reading:** [About custom agents](https://docs.github.com/copilot/concepts/agents/coding-agent/about-custom-agents) ~ [Creating custom agents](https://docs.github.com/copilot/how-tos/use-copilot-agents/coding-agent/create-custom-agents)

---

### MCP Servers (Model Context Protocol)

Connect Copilot to external tools, databases, and services through the Model Context Protocol.

- **Extend Copilot's reach** - Give Copilot access to your internal APIs, documentation, and tools
- **Custom integrations** - Build MCP servers that connect to your organization's systems
- **Community servers** - Leverage pre-built MCP servers for popular services

> 📖 **Further Reading:** [Using MCP servers with Copilot](https://docs.github.com/copilot/customizing-copilot/extending-copilot-chat-with-mcp)

---

### Copilot CLI

Bring GitHub Copilot's AI assistance directly to your terminal with **Copilot CLI**-a command-line interface that helps you work smarter without leaving your shell.

**Local development tasks:**
- **Make code changes** - *"Change the background-color of H1 headings to dark blue"*
- **Explore Git history** - *"Show me the last 5 changes made to CHANGELOG.md with who changed it and why"*
- **Improve your code** - *"Suggest improvements to content.js"* or *"Rewrite the readme to make it more accessible"*
- **Git operations** - *"Commit these changes"* or *"Revert the last commit, leaving changes unstaged"*
- **Scaffold applications** - *"Use create-next-app and Tailwind to create a dashboard that tracks build metrics from the GitHub API"*
- **Debug issues** - Tell Copilot when something isn't working and ask it to fix the problem

**GitHub.com integration:**
- **Track your work** - *"List my open PRs"* or *"List all open issues assigned to me in OWNER/REPO"*
- **Work on issues** - *"I've been assigned issue #1234. Start working on this in a suitably named branch."*
- **Create pull requests** - *"Add a script and create a PR to add it to the repo"*
- **Review PRs** - *"Check the changes in PR #57575 and report any serious errors"*
- **Manage PRs** - *"Merge all my open PRs in this repo"* or *"Close PR #11"*
- **Create issues** - *"Raise an issue about this unclosed file handle in somefile.py"*
- **Find issues** - *"Find good first issues for a new team member"*
- **GitHub Actions** - *"Create a workflow that runs eslint on PRs and fails if errors are found"*

> 📖 **Further Reading:** [About Copilot CLI](https://docs.github.com/en/copilot/concepts/agents/about-copilot-cli) ~ [Getting started with Copilot CLI](https://github.blog/ai-and-ml/github-copilot/github-copilot-cli-how-to-get-started/) ~ [GitHub repository](https://github.com/github/copilot-cli)

---

### Copilot Memory

Enable Copilot to build a persistent understanding of your repository over time-just like a new team member learning the codebase.

- **Repository-scoped memories** - Copilot stores tightly scoped pieces of information it learns while working on your code
- **Cross-feature knowledge** - Memories from Coding Agent can inform Code Review, and vice versa
- **Self-validating** - Copilot checks memories against the current codebase before using them
- **Auto-maintained** - Memories expire after 28 days unless revalidated, preventing stale information

**Example:** If Copilot Coding Agent discovers how your repository handles database connections, Copilot Code Review can later apply that knowledge to spot inconsistent patterns in pull requests.

> 📖 **Further Reading:** [About agentic memory for GitHub Copilot](https://docs.github.com/copilot/concepts/agents/copilot-memory) ~ [Announcement](https://github.blog/changelog/2025-12-19-copilot-memory-early-access-for-pro-and-pro/)

---

### Copilot Spaces

Centralize your project context so Copilot delivers smarter, more relevant responses grounded in your work.

- **Subject matter expert** - Ground Copilot's knowledge in curated code, docs, specs, and custom instructions
- **Always up to date** - Files and repositories added to a space stay current as they change
- **Scale expertise** - Share spaces across your organization to accelerate every developer on your team
- **Custom instructions** - Add space-specific instructions to further tailor Copilot's answers

> 📖 **Further Reading:** [Using Copilot Spaces](https://docs.github.com/copilot/how-tos/provide-context/use-copilot-spaces/use-copilot-spaces) ~ [Creating Spaces](https://docs.github.com/copilot/how-tos/provide-context/use-copilot-spaces/create-copilot-spaces) ~ [Announcement](https://github.blog/changelog/2025-05-29-introducing-copilot-spaces-a-new-way-to-work-with-code-and-context/)

---

### Prompt Engineering & Best Practices

Get more out of Copilot by learning how to communicate with it effectively.

- **Writing effective prompts** - Structure your requests for better results
- **Providing context** - Help Copilot understand what you need
- **Iterating on responses** - Refine and improve AI-generated code

> 📖 **Further Reading:** [Best practices for using GitHub Copilot](https://docs.github.com/copilot/using-github-copilot/best-practices-for-using-github-copilot)

---

## 📚 Essential Resources

### Documentation & Learning

| Resource | Description |
|----------|-------------|
| [GitHub Copilot Docs](https://docs.github.com/copilot) | Official documentation for all Copilot features |
| [GitHub Skills](https://skills.github.com/) | Interactive courses to level up your skills |
| [GitHub Blog](https://github.blog/tag/github-copilot/) | Latest news and announcements |
| [GitHub Changelog](https://github.blog/changelog/label/copilot/) | Stay updated on new features |

### Trust & Security

| Resource | Description |
|----------|-------------|
| [Copilot Trust Center](https://copilot.github.trust.page/) | Privacy, security, and responsible AI information |
| [GitHub Trust Center](https://trust.github.com/) | Security practices, compliance, and data protection policies |

### Community

| Resource | Description |
|----------|-------------|
| [GitHub Community Discussions](https://github.com/orgs/community/discussions/categories/copilot-conversations) | Ask questions and share knowledge |
| [GitHub YouTube](https://www.youtube.com/@GitHub) | Video tutorials and demos |

---

## 🙏 Thank You!

Thank you for joining us on this journey into AI-assisted development. The skills you've learned today will serve you well as AI continues to transform how we build software.

Remember:
- **You're still the pilot** - AI assists, but you make the decisions
- **Review AI-generated code** - Always verify before committing
- **Keep learning** - The best developers continuously adapt and grow
- **Share your knowledge** - Help others discover the power of AI assistance

---

**Happy coding!** 🚀
