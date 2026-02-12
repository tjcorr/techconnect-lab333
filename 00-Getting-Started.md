# Lab Overview

**Duration:** ~1 hour

Welcome to this hands-on lab where you'll go from GitHub Copilot basics to advanced productivity techniques! You'll work with **Octocat Supply**, a full-stack e-commerce application used by both GitHub and Microsoft to showcase Copilot and the rest of the GitHub platform.

### What You'll Learn

| Section | Duration | Key Skills |
|---------|----------|------------|
| **Lab Overview** | 5 min | Setup dev environment |
| [**Exercise 1: Copilot Basics**](./01-Copilot-Basics.md)| 10 min | Code completions, Copilot Chat, Modes & Models |
| [**Exercise 2: Agent Mode**](./02-Agent-Mode.md) | 15 min | Plan Mode, Agent Mode, vision capabilities, review workflow |
| [**Exercise 3: GitHub Platform**](./03-GitHub-Platform.md)  | 20 min | Copilot Coding Agent, Code Review, AI Autofix |
| [**What's Next**](./04-Whats-Next.md)  | 10 min | Custom instructions, custom agents, MCP, memory, spaces |

---

## The Octocat Supply Story

You've just joined **Octocat Supply**, a company bringing smart AI technology to cat products. You're part of the engineering team maintaining their flagship application, which includes:

- **API Layer** (/api) - TypeScript/Express backend with SQLite
- **Frontend** (/frontend) - React application with modern UI

> 💡 **Don't worry if these technologies are new to you.** Copilot will help with the heavy lifting, and you can ask it to explain anything unfamiliar as you go.

Let's get started! 🚀

---

## 📋 Prerequisites

## Step 1: Log in to GitHub

Before you begin this lab you will need to be logged into GitHub and have a Copilot Pro, Copilot Pro+, Copilot Business or Copilot Enterprise license. The lab also assumes you have Visual Studio Code and basic development tools like npm and make. This lab also works well in a Codespace for cloud based development if you don't have the necessary prereqs.

## Step 2: Create a New Repository from Template

You'll now create your own copy of the project by using a template repository.

1. Navigate to: 
```
https://github.com/octodemo/octocat_supply
```
2. Click the green **Use this template** button (located near the top-right of the page)
3. Ensure that **Include all branches** is set to **On**
4. Name your new repository:
   - **Owner:** Select a suitable organization or your personal account
   - **Repository name:** Choose a unique name you'll remember (e.g., **yourid-octocat-supply**)
5. Click the green **Create repository** button at the bottom of the page

> ℹ️ **Note:** It may take several seconds for the repository to be created.

## Step 3: Open the Project in VS Code

Now you'll clone (download) your new repository to your local machine and open it in Visual Studio Code.

### Clone the Repository

1. Open **Visual Studio Code** from the Start menu or taskbar
2. Open the Source Control panel by pressing **Ctrl + Shift + G**
3. Click **Clone Repository**
4. At the top of the window, click **Clone from GitHub**

### Authorize GitHub Access

5. Click **Allow** to continue signing in
6. In your web browser, click **Continue**
7. Click **Authorize** to grant VS Code access to GitHub
8. Click **Open** to navigate back to VS Code

### Select and Open Your Repository

9. From the dropdown list, select the repository you created in Step 2
10. Choose a folder to save the project (the default location is fine)
11. When prompted to "Sign in with your browser," click the button to proceed
12. Click **Authorize** again if prompted
13. Return to VS Code
14. Click **Open** to open the repository in your current window
15. When asked "Do you trust the authors?", click **Yes, I trust the authors**

## Step 4: Install Dependencies

Finally, you'll install the required project dependencies using the terminal.

1. Open the integrated terminal in VS Code:
   - Go to **Terminal** > **New Terminal** in the menu bar, or
   - Press **Ctrl + Shift + `** (backtick key)
2. In the terminal, type the following command and press **Enter**:
```
make install
```
3. Wait for the installation to complete before proceeding

> ℹ️ **Note:** This command will download and install all the packages needed for the project to run. Depending on your machine and network connection it make take a few minutes complete.

## Step 5: Verify GitHub Copilot is Working

Before proceeding, let's make sure GitHub Copilot is enabled and ready to use.

1. Look at the **Status Bar** at the bottom of VS Code
2. Hover over the **Copilot icon** that reads **Finish setup**
3. Click **Use AI Features** to enable Copilot if prompted

> ℹ️ **Note:** If Copilot is already enabled, you'll see the icon without any warning indicators. You're all set!

**Next up:** [Exercise 1: Copilot Basics](./01-Copilot-Basics.md) - Let Copilot autonomously improve test coverage across multiple files! 🚀