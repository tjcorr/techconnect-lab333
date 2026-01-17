# LAB333 - Zero to Hero: Hands-On with GitHub Copilot

## 🎯 Lab Overview

**Duration:** ~1 hour

Welcome to this hands-on lab where you'll go from GitHub Copilot basics to advanced productivity techniques! You'll work with **Octocat Supply**, a full-stack e-commerce application used by both GitHub and Microsoft to showcase Copilot and the rest of the GitHub platform.

### What You'll Learn

| Section | Duration | Key Skills |
|---------|----------|------------|
| **Quick Start** | 5 min | Verify environment, understand the codebase |
| [**Exercise 1: Copilot Basics**](./01-Copilot-Basics.md) | 15 min | Code completions, Copilot Chat, Modes & Models |
| [**Exercise 2: Agent Mode**](./02-Agent-Mode.md) | 15 min | Plan Mode, Agent Mode, vision capabilities, review workflow |
| [**Exercise 3: GitHub Platform**](./03-GitHub-Platform.md) | 20 min | Copilot Coding Agent, Code Review, AI Autofix |
| [**What's Next**](./04-Whats-Next.md) | 5 min | Custom instructions, custom agents, MCP, memory, spaces |

---

## The Octocat Supply Story

You've just joined **Octocat Supply**, a company bringing smart AI technology to cat products. You're part of the engineering team maintaining their flagship application, which includes:

- **API Layer** (`/api`) - TypeScript/Express backend with SQLite
- **Frontend** (`/frontend`) - React application with modern UI


<!-- TODO add in a summary once we have the labs built out -->

Let's get started! 🚀

---

## 📋 Prerequisites

Before beginning, you'll need to set up your own copy of the Octocat Supply repository.

### Step 1: Create Your Repository from the Template

1. Navigate to the template repository: **[https://github.com/octodemo/octocat_supply](https://github.com/octodemo/octocat_supply)**

2. Click the green **"Use this template"** button near the top right of the page

3. Select **"Create a new repository"** from the dropdown

4. Configure your new repository:
   - **Owner**: Select your organization //TODO add exact org name
   - **Repository name**: `octocat_supply_<your_name>` (or a name of your choice)
   - **Description**: (optional) Add a description for your repository
   - **Visibility**: Choose **Private** 

5. Click **"Create repository"**

> 📖 For more details, see GitHub's documentation on [Creating a repository from a template](https://docs.github.com/repositories/creating-and-managing-repositories/creating-a-repository-from-a-template)

### Step 2: Clone the Repository Locally

1. On your new repository's page, click the green **"Code"** button

2. Copy the repository URL (HTTPS or SSH based on your preference)

3. Open your terminal and run:
   ```bash
   git clone <your-repository-url>
   ```
   Replace `<your-repository-url>` with the URL you copied

4. Navigate into the cloned directory:
   ```bash
   cd octocat_supply
   ```

> 📖 For more details, see GitHub's documentation on [Cloning a repository](https://docs.github.com/en/repositories/creating-and-managing-repositories/cloning-a-repository)

### Step 3: Open in VS Code

1. Open VS Code

2. Go to **File > Open Folder** (or press `Ctrl+K Ctrl+O` on Windows/Linux, `Cmd+K Cmd+O` on Mac)

3. Navigate to and select the `octocat_supply` folder you just cloned

4. If prompted, click **"Yes, I trust the authors"** to enable all VS Code features

**Alternative**: You can also open the folder directly from your terminal:
```bash
code .
```

> 💡 **Prefer cloud development?** This lab works great in GitHub Codespaces! On your repository page, click **Code → Codespaces → Create codespace on main**. 

### Step 4: Install Dependencies

Run the following command to install all project dependencies:

```bash
make install
```

This will install dependencies for both the API and frontend applications. Wait for the installation to complete before proceeding.

### Step 5: Verify GitHub Copilot

Make sure GitHub Copilot is ready to use:

1. Look for the **Copilot icon** in the VS Code status bar (bottom right)
2. If you see a Copilot icon with no warning indicators, you're signed in and ready!
3. If you see a warning or the icon is missing:
   - Click the Copilot icon and select **"Sign in to GitHub"**
   - Follow the prompts to authenticate with your GitHub account


---

**Ready?** Continue to [Exercise 1: Writing Tests with Autocomplete & Edit Mode](./01-Copilot-Basics.md)
