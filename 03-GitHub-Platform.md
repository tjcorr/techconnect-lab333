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

So far, you've used Copilot as your coding companion in VS Code. But GitHub Copilot is designed to uplevel the **entire software development lifecycle**-from planning to coding to reviewing to deploying.

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
```
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

4. Click **Create** to submit the issue

> 💡 **Pro Tip:** Well-structured issues with clear requirements help both human developers AND AI agents understand what needs to be done.

> 🤖 **Even Easier with Copilot Chat:** You can ask Copilot to create issues for you directly on GitHub!
> 
> 1. Go to [github.com/copilot](https://github.com/copilot)
> 2. Describe what you need, specifying your repository:
>    
>    In OWNER/REPO, create a feature request to add autocomplete suggestions to the product search bar
>    
> 3. Copilot drafts the issue with a title, body, and can even suggest labels and assignees
> 4. You can attach screenshots, create multiple issues at once, or even assign the issue directly to Copilot!
> 5. Review the draft and click **Create**
> 
> [Learn more about creating issues with Copilot](https://docs.github.com/en/copilot/how-tos/use-copilot-for-common-tasks/use-copilot-to-create-or-update-issues#creating-an-issue-with-copilot)

---

## Part 2: Assign the Issue to Copilot Coding Agent

Now for the magic! Instead of implementing this feature yourself, let's delegate it to **Copilot Coding Agent**-an AI agent that can work on issues asynchronously in the background.

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

1. Copilot reacts to the issue with a 👀 (eyes) emoji-this means it's starting work!
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

> 🎬 **It's like watching a developer work!** You can see Copilot reading files, making decisions, and writing code-all in real-time.

### Step 4: Review the Completed PR

Once Copilot finishes, take time to thoroughly review the pull request:

1. **Read the PR description** - Copilot explains its approach, what it implemented, and any decisions it made
2. **Review the code changes** - Click the **Files changed** tab to see all modifications and ensure they follow your project's patterns
3. **Check the screenshots** - Copilot often includes screenshots showing the implemented UI-review these to verify the feature looks correct
4. **Verify it meets your requirements** - Does the implementation match what you asked for? If something is missing or needs changes, you can reopen the session and leave a comment mentioning **@copilot** with your feedback-Copilot will resume work and address your request
5. **Mark as ready for review** - The PR starts as a draft. When you're satisfied, click **Ready for review** to move it out of draft state
6. **Run workflows manually** - GitHub Actions workflows don't run automatically on Copilot PRs. Click the **Actions** tab and manually trigger any CI/CD workflows you want to run (tests, linting, etc.)

> 💡 **Pro Tip:** Treat Copilot's PR like any other code review. Check for edge cases, verify the implementation matches the requirements, and ensure tests pass before merging.

---

## Part 3: The Orchestrator Mindset

Here's where things get really powerful. While Copilot is working on the autocomplete feature, **you could assign more issues to Copilot in parallel** or work on complex coding tasks yourself!

### The New Developer Workflow

**Traditional approach:** You work on tasks one at a time-finish Task 1, then start Task 2, then Task 3. Everything happens sequentially.

**With Copilot Coding Agent:** You assign Tasks 1, 2, and 3 to Copilot all at once. While the agents work in parallel, you can focus on complex problems that need human creativity. Then you review and merge the PRs as they complete. The result? Multiple tasks finished in the time it used to take for one!

You become an **orchestrator**-delegating work, reviewing output, and managing multiple workstreams simultaneously.

### Ways to Start Copilot Coding Agent

Now that you've seen how to assign an issue to Copilot, here are additional ways you can interact with Coding Agent:

| Method | How | Best For |
|--------|-----|----------|
| **Assign Issue** | Assign Copilot to any GitHub issue | Feature requests with clear requirements |
| **Agent Panel** | Use [github.com/copilot/agents](https://github.com/copilot/agents) to start tasks directly | Quick tasks without creating formal issues |
| **VS Code** | Use **#copilotCodingAgent** in Copilot Chat (requires [GitHub PR extension](https://marketplace.visualstudio.com/items?itemName=GitHub.vscode-pull-request-github)) | Hand off tasks while staying in your IDE |
| **GitHub CLI** | Run **gh agent-task create** from the command line | Terminal-based workflows |
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

> 💡 **If your Copilot Coding Agent PR isn't finished yet:** You can create a new pull request from the **feat/legal** branch which should already exist in your repository. Go to the **Pull requests** tab, click **New pull request**, select **feat/legal** as the compare branch, and click **Create pull request**. You can use this PR for the remaining steps.

2. Open the **Reviewers** menu in the right sidebar
3. Select **Copilot**
4. Wait for Copilot to complete the code review. You can also view the session just like we did with Copilot Coding Agent to see the agent's thought process.

### Step 2: Review the PR Overview Comment

Once Copilot finishes its review, start by reading the **Pull request overview** comment at the top. This summary gives you a high-level picture of Copilot's findings across the entire pull request, including:

- A summary of the major changes in the PR
- A brief description of each modified or new file
- An overall assessment of the code quality

This is a great way to quickly understand the scope and impact of the PR before diving into individual findings.

> ℹ️ **Note:** Copilot always leaves a "Comment" review-not "Approve" or "Request changes." This means Copilot's reviews don't count toward required approvals and won't block merging.

### Step 3: Review Individual Comments

From the overview, scroll down (or click through) to see Copilot's **inline comments** on specific lines of code. You'll notice two types of findings:

**Simple fixes with suggested changes:**
Some comments include a ready-made code suggestion that you can commit directly. For these:
- Click **Commit suggestion** to accept the fix and commit it right away
- Or click **Add suggestion to batch** to group multiple simple suggestions into a single commit

**More complex issues:**
For findings that require broader changes (e.g., refactoring, adding error handling across multiple lines), Copilot may not have an inline fix. For these:
- Click **Implement suggestion** to pass the finding to **Copilot Coding Agent**, which will create a commit addressing the issue
- This is a great example of **agents working together**-Copilot Code Review identifies the problem, and Copilot Coding Agent implements the solution!

You can also use 👍 or 👎 on any comment to provide feedback and help improve Copilot's suggestions over time, or click **Resolve** to dismiss a conversation you don't want to act on.

### Step 4: Implement All Suggestions at Once

If you'd like Copilot Coding Agent to tackle all the findings in one go, scroll back to the **Pull request overview** comment and click **Implement all suggestions**. This hands off every finding to Copilot Coding Agent, which will work through them and commit the fixes-saving you from addressing each one individually.

### Step 5: Request Re-review (Optional)

When you push new changes, Copilot won't automatically re-review. To request another review, click the **re-request review** button (🔄) next to Copilot's name in the Reviewers menu.

> 💡 **Pro Tips:**
> - You can [enable automatic reviews](https://docs.github.com/copilot/how-tos/agents/copilot-code-review/automatic-code-review) so Copilot reviews every PR automatically
> - Customize Copilot's reviews with [custom instructions](https://docs.github.com/copilot/customizing-copilot/adding-repository-custom-instructions-for-github-copilot) in a **.github/copilot-instructions.md** file. This repository already has some samples you can review!

> 📖 [Learn more about Copilot Code Review](https://docs.github.com/copilot/how-tos/use-copilot-agents/request-a-code-review/use-code-review?tool=webui)

---

## Part 5: Copilot Autofix for Code Scanning

GitHub Advanced Security (GHAS) includes **Copilot Autofix**, which automatically generates fixes for security vulnerabilities found by CodeQL code scanning. This feature is enabled by default for GHAS customers and free for all public repositories.

> ℹ️ **Note:** This is an informational section-no action required. Copilot Autofix works automatically when code scanning detects vulnerabilities.

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

> 🔒 **Found Means Fixed:** With Copilot Autofix, a vulnerability found becomes a vulnerability fixed-helping teams ship secure code faster.

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
