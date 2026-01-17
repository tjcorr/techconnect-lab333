# Exercise 2: Building Features with Agent Mode

⏱️ **Estimated Time:** 15 minutes

## 🎯 Learning Objectives

In this exercise, you'll experience the power of GitHub Copilot's agentic capabilities:

- **Plan Mode** - Let Copilot analyze requirements and create an implementation strategy
- **Agent Mode** - Hand the keyboard to Copilot and let it implement across multiple files
- **Vision Capabilities** - Use images as context for your prompts
- **Review Workflow** - Accept, reject, or modify Copilot's autonomous changes

---

## The Scenario: Adding a Shopping Cart

The Octocat Supply product team has a new feature request: customers need a shopping cart! Currently, when users click "Add to Cart" on the Products page, nothing actually happens - there's just a placeholder message.

Your mission: Implement a complete cart feature including:
- A Cart page to view and manage items
- A Cart icon in the navigation bar showing the item count
- The ability to add/remove items and see totals

Instead of writing this all yourself, you'll let Copilot drive while you supervise.

> 💡 **The Pair Programming Analogy:** Think of Agent mode as handing your laptop to your pair programming partner. You describe what you want, they write the code, and you review their work before committing.

---

## Part 1: See the Current State

Before we add the cart, let's see what we're working with.

### Step 1: Start the Application

If the application isn't already running, start it:

```bash
# From the project root
make dev
```

You can also use the `Start API & Frontend` task in VS Code.

### Step 2: Explore the Products Page

1. Open your browser and navigate to the app at `http://localhost:5173`
2. Click **"Products"** in the navigation bar
3. Try clicking **"Add to Cart"** on any product

**What happens?** You should see a brief message "Added to Cart" - but there's no actual cart functionality. No cart icon appears, and there's nowhere to view your cart. Let's fix that!

---

## Part 2: Plan the Implementation

Before diving into code, let's use **Plan mode** to create a structured implementation strategy. This is especially valuable for larger features that span multiple files.

### Step 1: Open Copilot Chat in Plan Mode

1. Open the Copilot Chat panel (`Ctrl+Alt+I` / `Cmd+Alt+I`)
2. Select **Plan** from the mode dropdown at the bottom of the panel

### Step 2: Add Visual Context

We have a design mockup for the cart. Let's give Copilot visual context:

1. Click the **paperclip icon** (📎) in the chat input, or drag and drop the file
2. Attach: `docs/design/cart.png`

> 💡 **Pro Tip:** Copilot can analyze images to understand UI requirements, color schemes, layouts, and component structure. This is incredibly powerful for implementing designs!

### Step 3: Describe the Feature

With the image attached, enter this prompt:

```
I need to plan for a simple Cart Page. I also want a Cart icon in the NavBar that shows the number of items in the Cart.
```

### Step 4: Review the Plan

Copilot will analyze the codebase and the design image, then generate a detailed implementation plan. You should see:

- **Files to create** - New components like CartPage, CartContext, etc.
- **Files to modify** - Updates to Navigation, routing, etc.
- **Implementation steps** - A logical order for the changes

Take a moment to review the plan:
- Does it make sense architecturally?
- Are there any approaches you'd want to change?
- Is anything missing?

Copilot might also ask for additional information in a **Further Considerations** section, such as:

> **Further Considerations**
> - Should the cart eventually submit orders via the existing `/orders` and `/order-details` API endpoints on checkout?
> - Add toast notifications for cart actions (added/removed items) instead of alerts?
> - Include product images in cart display similar to the attached screenshot?

You can continue chatting with Copilot to answer these questions or otherwise refine your plan until you are satisfied.

> 📖 **Further Reading:** [Using Plan mode in Copilot](https://docs.github.com/copilot/how-tos/chat-with-copilot/chat-in-ide#plan-mode)

---

## Part 3: Let Copilot Implement the Feature

Now for the exciting part! Let's have Copilot switch to Agent mode and implement this new feature for us.

### Step 1: Start the Implementation

At the bottom of your plan, click the **Start Implementation** button. This will automatically switch Copilot Chat to Agent mode and begin implementing the plan.

### Step 2: Watch Copilot Work

Copilot will now autonomously:
- Read your project to understand the current codebase
- Create new files (CartContext, CartPage component, etc.)
- Modify existing files (Navigation, App routing)
- Install any needed dependencies
- Run terminal commands if needed
- Self-heal if it encounters compilation errors, test failures, or other issues
- Utilize any needed tools / installed MCP servers to achieve your goal

You'll see Copilot's progress in the chat and in your editor as files are created and modified. You can follow along as it works to see how Copilot is working through the plan just like a developer would.

### Step 3: Review Each Change

As Copilot makes changes, you'll be presented with options:

- **Keep** ✓ - Accept the change
- **Undo** ✗ - Reject and revert the change
- **View diff** - See exactly what changed

For each file Copilot modifies:
1. Review the diff to understand what changed
2. Check that the code follows your project's patterns
3. Accept or reject based on quality

> 💡 **Best Practice:** Even though Copilot is "driving," you're still responsible for the code quality. Review changes thoughtfully, just as you would in a code review.

---

## Part 4: Verify the Implementation

Time to see if it works! Our application should have automatically hot-reloaded with the changes made. If not you can always rerun:

```bash
# From the project root
make dev
```

### Step 1: Test the Cart Functionality

1. Navigate to the **Products** page
2. Click **"Add to Cart"** on a few products
3. Look at the navigation bar - you should see a **cart icon with a badge** showing the number of items
4. Click the **cart icon** to navigate to the Cart page
5. On the Cart page, verify you can:
   - See all items you added
   - See the total price
   - Adjust quantities or remove items

### Step 2: Troubleshooting

**If something isn't working as expected:**

1. **Check the browser console** (`F12` or `Cmd+Option+I`)
   - Look for any error messages in red
   - These will help identify what went wrong

2. **Verify all files were saved**
   - Check for unsaved indicators (dots) in VS Code tabs
   - Save all files (`Cmd+K S` or `Ctrl+K S` to save all)

3. **Restart the development server**
   ```bash
   # Stop the current server (Ctrl+C in the terminal)
   make dev
   ```

4. **Ask Copilot for help**
   - Describe the specific error you're seeing
   - Share any console error messages
   - Copilot can help debug and fix issues

> 💡 **Don't worry if the cart isn't perfect!** AI-generated code isn't always flawless on the first try. If you encounter issues, continue iterating with Copilot to fix them—this back-and-forth is a natural part of working with AI assistants. If you're running short on time, feel free to move on to the next exercise.

### Step 3: Celebrate! 🎉

You just implemented a complete feature across multiple files without writing most of the code yourself. This is the power of agentic AI assistance!

---

## What Just Happened?

Think about what you just accomplished. You gave Copilot:
- A **single image** of a design mockup
- A **two-sentence description** of what you wanted

And Copilot:
- **Analyzed** your entire codebase to understand the project structure
- **Planned** a complete implementation strategy
- **Created** new components, context providers, and pages
- **Modified** existing files to integrate everything together
- **Followed** your project's existing patterns and conventions

This is the shift from AI as a "code autocomplete" to AI as a **collaborative developer** that can take on entire features while you focus on the bigger picture.

---

## 🎉 Exercise 2 Complete!

**What you accomplished:**
- ✅ Used **Plan mode** to create an implementation strategy
- ✅ Provided **visual context** with a design image
- ✅ Used **Agent mode** to autonomously implement a multi-file feature
- ✅ **Reviewed and accepted** Copilot's changes

**Key Takeaways:**
1. **Plan before implementing** - Plan mode helps you think through complex features before writing code
2. **Images are powerful context** - Copilot can interpret designs and implement them
3. **Agent mode is collaborative** - You describe, Copilot implements, you review
4. **You're still the pilot** - Always review AI-generated code before accepting it

---

## 📚 Additional Resources

- [GitHub Copilot Agent Mode](https://docs.github.com/copilot/using-github-copilot/using-copilot-in-the-command-line)
- [Vision capabilities in Copilot](https://github.blog/changelog/2024-05-copilot-chat-vision/)
- [Best practices for prompting Copilot](https://docs.github.com/copilot/using-github-copilot/best-practices-for-using-github-copilot)

---

**Next up:** [Exercise 3: GitHub Platform and Agentic AI](./03-GitHub-Platform.md) - Take Copilot beyond the IDE with Coding Agent, Code Reviews, and more! 🚀
