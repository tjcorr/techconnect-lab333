# Exercise 3: GitHub Platform and Agentic AI

⏱️ **Estimated Time:** 20 minutes

## 🎯 Learning Objectives

In this exercise, you'll discover that GitHub Copilot extends far beyond the IDE:

- **Copilot Coding Agent** - Delegate entire tasks to an AI agent that works asynchronously
- **Orchestration Mindset** - Kick off multiple tasks in parallel and track their progress
- **Copilot Code Review** - Get AI-powered code reviews on any pull request
- **AI Autofix** - Automatically fix security vulnerabilities with GitHub Advanced Security

---

## The Big Picture: AI Across the Entire SDLC

So far, you've used Copilot as your coding companion in VS Code. But GitHub Copilot is designed to uplevel the **entire software development lifecycle**—from planning to coding to reviewing to deploying.

In this exercise, we'll explore the GitHub platform features that let you delegate work to AI agents and review their output.

---

## Part 1: Create an Issue for a New Feature

Let's start by creating a GitHub Issue for a feature we want to implement: **autocomplete suggestions for the search bar**.

### Step 1: Navigate to GitHub Issues

1. Open your repository on GitHub.com
2. Click the **Issues** tab
3. Click **New issue**

### Step 2: Create the Issue

Create an issue with the following details:

**Title:**
```
Add autocomplete suggestions to the product search bar
```

**Description:**
```markdown
## Summary
Add autocomplete/typeahead functionality to the product search bar that suggests products as the user types.

## Requirements
- Show suggestions after typing 2+ characters
- Display up to 5 matching products
- Show product name and category in suggestions
- Clicking a suggestion should navigate to that product or filter the list
- Suggestions should be styled consistently with our existing UI (support dark mode)

## Technical Notes
- The search bar is in the Products component
- Use the existing products data/API
- Consider debouncing the search input for performance

## Acceptance Criteria
- [ ] Autocomplete dropdown appears when typing
- [ ] Suggestions update as user types
- [ ] Selecting a suggestion filters/navigates appropriately
- [ ] Works in both light and dark mode
- [ ] Mobile-friendly
```

4. Click **Submit new issue**

> 💡 **Pro Tip:** Well-structured issues with clear requirements help both human developers AND AI agents understand what needs to be done.

> 🤖 **Even Easier with Copilot Chat:** You can ask Copilot to create issues for you directly on GitHub!
> 
> 1. Go to [github.com/copilot](https://github.com/copilot)
> 2. Describe what you need, specifying your repository:
>    ```
>    In OWNER/REPO, create a feature request to add autocomplete suggestions to the product search bar
>    ```
> 3. Copilot drafts the issue with a title, body, and can even suggest labels and assignees
> 4. You can attach screenshots, create multiple issues at once, or even assign the issue directly to Copilot!
> 5. Review the draft and click **Create**
> 
> [Learn more about creating issues with Copilot](https://docs.github.com/en/copilot/how-tos/use-copilot-for-common-tasks/use-copilot-to-create-or-update-issues#creating-an-issue-with-copilot)

---

## Part 2: Assign the Issue to Copilot Coding Agent

Now for the magic! Instead of implementing this feature yourself, let's delegate it to **Copilot Coding Agent**—an AI agent that can work on issues asynchronously in the background.

### Step 1: Assign Copilot to the Issue

1. On your newly created issue, look at the right sidebar
2. Click **Assignees**
3. Select **Copilot** from the list

That's it! Copilot Coding Agent will now:
- Read and understand the issue
- Analyze your codebase
- Create a branch
- Implement the feature
- Open a draft Pull Request

### Step 2: Watch the Magic Happen

After assigning the issue:

1. Copilot reacts to the issue with a 👀 (eyes) emoji—this means it's starting work!
2. Shortly after, a new **Draft Pull Request** will be created and linked to the issue
3. Click the PR link in the issue to navigate to the pull request

### Step 3: Follow Along with the Session

On the Pull Request page:

1. Look for the **"View session"** button at the bottom of the timeline.
2. Click it to open the live session view
3. Watch Copilot work in real-time! You'll see:
   - Copilot's thought process and planning
   - Files being read and analyzed
   - Code being written and committed
   - Terminal commands being executed
   - Any questions or blockers Copilot encounters
4. You can also steer the session while Copilot is running to add additional context or suggestions.

> 🎬 **It's like watching a developer work!** You can see Copilot reading files, making decisions, and writing code—all in real-time.

### Step 4: Review the Changes

As Copilot works, the PR updates with its progress:

- **Commits** - Each logical change Copilot made
- **Files changed** - All the code modifications
- **PR description** - Copilot explains its approach and what it implemented

Take a moment to review the code changes in the "Files changed" tab. Does the implementation look reasonable? Does it follow the patterns in your codebase?

---

## Part 3: The Orchestrator Mindset

Here's where things get really powerful. While Copilot is working on the autocomplete feature, **you could assign more issues to Copilot in parallel** or work on complex coding tasks yourslef!

### The New Developer Workflow

```
Traditional:              With Copilot Coding Agent:
                         
You → Task 1             You → Assign Task 1 to Copilot
     ↓                        Assign Task 2 to Copilot
You → Task 2                  Assign Task 3 to Copilot
     ↓                             ↓
You → Task 3             Review PR 1 ✓
     ↓                   Review PR 2 ✓
Done (sequential)        Review PR 3 ✓
                         Done (parallel!)
```

You become an **orchestrator**—delegating work, reviewing output, and managing multiple workstreams simultaneously.

### Ways to Start Copilot Coding Agent

Now that you've seen how to assign an issue to Copilot, here are additional ways you can interact with Coding Agent:

| Method | How | Best For |
|--------|-----|----------|
| **Assign Issue** | Assign Copilot to any GitHub issue | Feature requests with clear requirements |
| **Agent Panel** | Use [github.com/copilot/agents](https://github.com/copilot/agents) to start tasks directly | Quick tasks without creating formal issues |
| **VS Code** | Use `#copilotCodingAgent` in Copilot Chat (requires [GitHub PR extension](https://marketplace.visualstudio.com/items?itemName=GitHub.vscode-pull-request-github)) | Hand off tasks while staying in your IDE |
| **GitHub CLI** | Run `gh agent-task create` from the command line | Terminal-based workflows |
| **Azure DevOps** | Assign Azure Boards work items to Copilot | Teams using Azure DevOps for planning |

> 📖 [Learn more about all the ways to start Coding Agent](https://docs.github.com/copilot/how-tos/use-copilot-agents/coding-agent/create-a-pr)

### Track All Your Agents

To see all your running Copilot agents:

1. Go to your repository on GitHub
2. Click on **Copilot** in the repository navigation
3. Select **Coding agent** to see the agents dashboard

Here you can:
- See all active sessions
- View completed work
- Track progress across multiple tasks
- Jump into any session to observe or interact

> 💡 **Scaling Your Impact:** Imagine starting your day by triaging issues and assigning 5-10 to Copilot. By your first coffee break, you have multiple PRs ready for review!

---

## Part 4: AI-Powered Code Review

When Copilot Coding Agent finishes (or for any PR, human or AI-authored), you can use **Copilot Code Review** to get AI-powered feedback.

### Step 1: Request a Copilot Review

1. Open the PR that Copilot created (or any pull request)
2. Open the **Reviewers** menu in the right sidebar
3. Select **Copilot**
4. Wait for Copilot to review—this usually takes less than 30 seconds

### Step 2: Review the Feedback

Scroll down and read through Copilot's comments. Where possible, Copilot's feedback includes **suggested changes** which you can apply with a couple of clicks.

> ℹ️ **Note:** Copilot always leaves a "Comment" review—not "Approve" or "Request changes." This means Copilot's reviews don't count toward required approvals and won't block merging.

### Step 3: Work with Suggestions

For each suggestion, you can:
- **Apply** - Accept the suggestion and commit it directly
- **Batch apply** - Accept multiple suggestions together in a single commit
- **Implement suggestion** - Click to have Copilot Coding Agent implement more complex changes
- **Provide feedback** - Use 👍 or 👎 to help improve Copilot's suggestions
- **Resolve** - Dismiss the conversation if you don't want to act on it

### Step 4: Request Re-review (Optional)

When you push new changes, Copilot won't automatically re-review. To request another review, click the **re-request review** button (🔄) next to Copilot's name in the Reviewers menu.

> 💡 **Pro Tips:**
> - You can [enable automatic reviews](https://docs.github.com/copilot/how-tos/agents/copilot-code-review/automatic-code-review) so Copilot reviews every PR automatically
> - Customize Copilot's reviews with [custom instructions](https://docs.github.com/copilot/customizing-copilot/adding-repository-custom-instructions-for-github-copilot) in a `.github/copilot-instructions.md` file

> 📖 [Learn more about Copilot Code Review](https://docs.github.com/copilot/how-tos/use-copilot-agents/request-a-code-review/use-code-review?tool=webui)

---

## Part 5: Copilot Autofix for Code Scanning

GitHub Advanced Security (GHAS) includes **Copilot Autofix**, which automatically generates fixes for security vulnerabilities found by CodeQL code scanning. This feature is enabled by default for GHAS customers and free for all public repositories.

> ℹ️ **Note:** This is an informational section—no action required. Copilot Autofix works automatically when code scanning detects vulnerabilities.

### How It Works

When CodeQL finds a vulnerability in your code (either in a pull request or existing code):

1. **Detection** - CodeQL identifies a security vulnerability
2. **AI Analysis** - Copilot analyzes the alert, surrounding code, and best practices
3. **Fix Generation** - A suggested fix with explanation is generated automatically
4. **One-Click Apply** - Apply the fix directly or create a PR with the changes

### The Impact: Fix Vulnerabilities 3x Faster

Based on GitHub's data, developers using Copilot Autofix remediate vulnerabilities significantly faster:

| Vulnerability Type | With Autofix | Manual Fix | Speed Improvement |
|-------------------|--------------|------------|-------------------|
| Overall | 28 minutes | 1.5 hours | **3x faster** |
| Cross-site scripting (XSS) | 22 minutes | ~3 hours | **7x faster** |
| SQL injection | 18 minutes | 3.7 hours | **12x faster** |

### Supported Languages

Copilot Autofix generates fixes for vulnerabilities in: **C#, C/C++, Go, Java/Kotlin, JavaScript/TypeScript, Python, Ruby, Rust, and Swift**.

### Two Key Use Cases

1. **Keep new vulnerabilities out** - Autofix in pull requests helps developers fix issues before they merge
2. **Pay down security debt** - Generate fixes for existing alerts to tackle your backlog of vulnerabilities

> 🔒 **Found Means Fixed:** With Copilot Autofix, a vulnerability found becomes a vulnerability fixed—helping teams ship secure code faster.

> 📖 Learn more: [Responsible use of Copilot Autofix](https://docs.github.com/code-security/responsible-use/responsible-use-autofix-code-scanning) | [Copilot Autofix announcement](https://github.blog/news-insights/product-news/secure-code-more-than-three-times-faster-with-copilot-autofix/)

---

## 🎉 Exercise 3 Complete!

**What you accomplished:**
- ✅ Created an issue and assigned it to **Copilot Coding Agent**
- ✅ Watched Copilot work and followed along with its session
- ✅ Learned the **orchestrator mindset** for parallel task delegation
- ✅ Discovered multiple ways to invoke Copilot Coding Agent
- ✅ Used **Copilot Code Review** for AI-powered PR feedback
- ✅ Learned about **AI Autofix** for security vulnerabilities

**Key Takeaways:**
1. **Copilot spans the entire SDLC** - From planning to coding to reviewing to securing
2. **Delegation scales your impact** - Assign multiple tasks and review in parallel
3. **AI reviews catch issues** - Get feedback on any PR, human or AI-authored
4. **Security gets easier** - Copilot Autofix removes friction from vulnerability fixes

---

**Next up:** [What's Next: Your Copilot Journey Continues](./04-Whats-Next.md) - Discover advanced features and resources to master GitHub Copilot! 🚀
