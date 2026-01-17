# Exercise 1: Writing Tests with Copilot Basics

⏱️ **Estimated Time:** 15 minutes

## 🎯 Learning Objectives

In this exercise, you'll learn the foundational ways to interact with GitHub Copilot:

- **Code Completions** - Copilot's inline suggestions as you type
- **Copilot Chat** - Conversational AI assistance for larger tasks
- **Modes & Models** - Understanding the different ways to interact with Copilot

---

## The Scenario: Improving Test Coverage

The Octocat Supply engineering team has been focused on shipping features, and test coverage has fallen behind. As the newest team member, you've been tasked with improving the test suite for the API layer.

Looking at the codebase, you'll notice:
- ✅ `api/src/routes/branch.test.ts` - Has tests (we'll add more!)
- ❌ `api/src/routes/product.ts` - No tests yet!

Let's use Copilot to write tests efficiently and see how different interaction patterns work.

---

## Part 1: Code Completions (Ghost Text)

Code completions are Copilot's most seamless feature - suggestions appear as "ghost text" while you type, and you simply press `Tab` to accept them.

### Step 1: Open the Branch Test File

1. Open `api/src/routes/branch.test.ts` in VS Code
2. Take a moment to review the existing tests - notice they cover basic CRUD operations

### Step 2: Add a New Test with Copilot's Help

Let's add a test for an edge case: what happens when you try to update a non-existent branch?

1. **Position your cursor** at the end of the file, just before the final `});`

2. **Start typing** a new test:
   ```typescript
   it('should return 404 when updating non-existent branch',
   ```

3. **Watch for ghost text** - Copilot will suggest the rest of the test function

4. **Press `Tab`** to accept the suggestion, or keep typing to refine it.

   > 💡 **Note:** Copilot may only suggest part of the solution at a time. You might need to press `Tab` multiple times to generate the full test, as Copilot builds up the code incrementally.

5. If the suggestion isn't quite right:
   - Press `Esc` to dismiss
   - Press `Alt+]` (Windows/Linux) or `Option+]` (Mac) to see alternative suggestions
   - Continue typing to guide Copilot toward what you want

### What You Should See

Copilot should generate something similar to:

> ⚠️ **Note:** Copilot is non-deterministic, meaning each response can vary. You might get a different test implementation than shown below - that's completely normal! The important thing is that your test follows the same patterns and structure as the existing tests in the file.

```typescript
it('should return 404 when updating non-existent branch', async () => {
  const updatedBranch = {
    headquartersId: 1,
    name: 'Ghost Branch',
    description: 'This branch does not exist',
    address: '000 Nowhere St',
    contactPerson: 'Nobody',
    email: 'nobody@test.com',
    phone: '555-0000',
  };
  const response = await request(app).put('/branches/999').send(updatedBranch);
  expect(response.status).toBe(404);
});
```

> 💡 **Tip:** Copilot learns from context! It saw the other tests in the file and matched the style, imports, and patterns automatically.

### Step 3: Verify Your Test Works

Copilot-generated code isn't guaranteed to be perfect! Even though it may look good, you should review it like any other code before running it for correctness, security vulnerabilities, and to ensure it meets your requirements. This is good practice regardless of the source. Once you're satisfied with the test that Copilot wrote, run the test suite to make sure your new test passes:

```bash
make test
```

> 💡 **Tip:** If you see an error like `vitest: command not found` or `make: *** [test] Error 127`, you need to run `make install` first to install the dependencies.

> 📖 **Further Reading:** [Using GitHub Copilot code suggestions](https://docs.github.com/copilot/using-github-copilot/getting-code-suggestions-in-your-ide-with-github-copilot)

---

## Part 2: Copilot Chat - Your AI Pair Programmer

While code completions are great for incremental work, **Copilot Chat** excels at larger tasks like generating entire test files, explaining code, or brainstorming solutions. Think of Copilot Chat as your AI pair programmer that you can have natural conversations with about your code, ask questions, and request changes without needing to write everything yourself. It's particularly useful when you need to understand unfamiliar code, scaffold new features, or get help debugging complex issues. Before we jump in let's learn about the basics:

### Chat Modes

There are several modes to interact with GitHub Copilot:

| Mode | Purpose | Best For |
|------|---------|----------|
| **Ask** | Get explanations and answers about code | Understanding existing code, learning new concepts |
| **Edit** | Modify existing code with AI assistance | Refactoring, bug fixes, feature additions |
| **Plan** | Create step-by-step implementation strategies before coding | Planning new features, designing implementation |
| **Agent** | Delegate complex tasks to AI | Multi-file changes, autonomous implementation (we'll cover this in Exercise 2!) |

To switch between modes, use the agents dropdown at the bottom of the chat view. For this exercise let's use `Edit` mode.

> 📖 **Further Reading:** [Copilot Chat modes](https://docs.github.com/copilot/how-tos/chat-with-copilot/chat-in-ide#copilot-chat-chat-modes)

### Choosing the Right AI Model

GitHub Copilot Chat offers access to multiple AI models, each with different strengths and capabilities. Understanding when to use each model can significantly improve your development experience.

#### Available Models

GitHub Copilot provides access to several AI models from leading providers such as OpenAI, Anthropic, Google, and others. The available options are constantly evolving. For the most up-to-date information about supported models and their capabilities, see the official documentation: [GitHub Copilot Supported Models](https://docs.github.com/copilot/reference/ai-models/supported-models)

Different models excel at different types of tasks. For detailed information about each model's strengths and ideal use cases, see the [AI Models Comparison Guide](https://docs.github.com/copilot/reference/ai-models/model-comparison):
- Some are optimized for **code understanding and analysis**
- Others excel at **complex reasoning and problem-solving**
- Some prioritize **speed for quick responses**
- Others focus on **detailed explanations and accuracy**

GitHub is now also offering a new auto model selection feature within Visual Studio Code that automatically chooses the best model for your specific task based on context and requirements. This can help streamline your workflow by ensuring you're always using the most suitable AI model without manual selection. More information can be found here: [Auto Model Selection](https://docs.github.com/copilot/concepts/auto-model-selection).


To switch between models, use the model dropdown at the bottom of the chat view. For this exercise let's use `Auto` model.

> 💡 **Pro Tip:** Try asking the same question to different models to compare their responses! Each model may provide unique insights or different perspectives on the same problem.

> 📖 **Further Reading:** [Changing your AI model for Copilot Chat](https://docs.github.com/copilot/how-tos/use-ai-models/change-the-chat-model#changing-the-ai-model-1)

---

Now that we've learned about Copilot Chat, let's implement all the tests needed for the product route:

### Step 1: Open the Product Routes File

1. Open `api/src/routes/product.ts`
2. Notice this file has no corresponding test file yet!

### Step 2: Open Copilot Chat

Open the Copilot Chat panel:
- Click the **Copilot icon** in the sidebar, or
- Press `Ctrl+Alt+I` (Windows/Linux) or `Cmd+Alt+I` (Mac)
- Make sure you are on `Edit` mode and select a model of your choice (such as Claude Sonnet 4.5)

> 📖 **Additional Help:** [Access Chat in VS Code](https://code.visualstudio.com/docs/copilot/chat/copilot-chat#_access-chat-in-vs-code)

### Step 3: Generate Tests with Chat

In the Chat panel, type the following prompt:

```
Generate tests for #file:product.ts with a data model defined at #file:product.ts following the patterns used in #file:branch.test.ts 
```

Note you can't just copy/paste this command since we want to reference particular files. When you type `#` in the chat it will bring up a menu where you can select the correct file. You will want to make sure to attach:
- `api/src/routes/product.ts` (the routes file to test)
- `api/src/models/product.ts` (the data model)
- `api/src/routes/branch.test.ts` (the test patterns to follow)

> 💡 **Pro Tip:** The `#file:` syntax explicitly references files in your workspace, giving Copilot precise context. You can also drag and drop files directly into the chat, click the **paperclip icon** to attach files, or link to your open editors! Adding context helps Copilot better understand what you are trying to do.

> 📖 **Further Reading:** [Copilot Chat Context](https://code.visualstudio.com/docs/copilot/chat/copilot-chat-context) - Learn more about the different ways to provide context to Copilot.

### Step 4: Review and Apply the Generated Code

Copilot will generate a comprehensive test file. Review the output:

1. **Check the test structure** - Does it match your project's patterns?
2. **Verify the assertions** - Are they testing the right behaviors?
3. **Look for edge cases** - Did Copilot include error scenarios?

> ⚠️ **Important:** Always review Copilot-generated code before using it! Copilot is a powerful tool, but it can make mistakes, hallucinate APIs that don't exist, or miss edge cases. You are responsible for the code you commit - treat Copilot suggestions as a starting point, not a final answer.

### Step 5: Run the New Tests

Verify everything works:

```bash
make test
```

> 💡 **Don't worry if some tests fail!** AI-generated code isn't always perfect on the first try. If you encounter failing tests, you can continue iterating with Copilot to fix any issues. Simply share the error message in the chat and ask Copilot to help diagnose and resolve the problem - this iterative workflow is a natural part of working with AI assistants. If you're running short on time, feel free to move on to the next exercise - the rest of the exercises don't depend on it.

---

## 🎉 Exercise 1 Complete!

**What you accomplished:**
- ✅ Used **code completions** to add a test with natural typing flow
- ✅ Used **Copilot Chat** to generate an entire test file
- ✅ Learned about **modes** and **model selection**

**Key Takeaways:**
1. **Code completions** = seamless, inline, great for incremental work
2. **Copilot Chat** = conversational, great for larger tasks and explanations
3. **Context matters** - referencing files helps Copilot give better suggestions

---

## 📚 Additional Resources

- [GitHub Copilot Documentation](https://docs.github.com/en/copilot)
- [GitHub Copilot Blog](https://github.blog/tag/github-copilot/)
- [Copilot Tips and Tricks](https://docs.github.com/copilot/using-github-copilot/best-practices-for-using-github-copilot)
- [GitHub Copilot in VS Code](https://code.visualstudio.com/docs/copilot/overview)

---

**Next up:** [Exercise 2: Agent Mode](./02-Agent-Mode.md) - Let Copilot autonomously improve test coverage across multiple files! 🚀
