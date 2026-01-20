# Installation Guide

This guide walks you through setting up Agile-AI on your machine. The framework runs inside Visual Studio Code using the OpenCode extension, which provides the AI coding assistant functionality. By the end of this guide, you will have a working environment where you can invoke the three agents and begin developing software using the structured workflow.

The installation process is the same whether you are using macOS or Windows. Where there are platform-specific differences, both options are provided.

---

## Prerequisites

Before installing the framework, you need to set up your development environment. This section explains each component and why it is required.

### Visual Studio Code

Visual Studio Code (VS Code) is the integrated development environment where you will work with the AI agents. It provides the editor, file management, terminal access, and extension ecosystem that the framework relies on. VS Code is free, open-source, and runs on macOS, Windows, and Linux.

**Installation:**

- **macOS:** Download from [code.visualstudio.com](https://code.visualstudio.com/), open the downloaded `.zip` file, and drag the application to your Applications folder.
- **Windows:** Download the installer from [code.visualstudio.com](https://code.visualstudio.com/) and run it. The default installation options are suitable for most users.

After installation, launch VS Code to verify it works correctly.

### Git (Recommended)

Git is a version control system that tracks changes to your project over time. The Sprinter agent uses Git to commit completed sprints, creating a history of your project's development. While not strictly required for exploring the framework, Git is essential for the full workflow.

**Installation:**

- **macOS:** Git is often pre-installed. Open Terminal and type `git --version`. If not installed, you will be prompted to install the Xcode Command Line Tools, or you can download Git from [git-scm.com](https://git-scm.com/).
- **Windows:** Download the installer from [git-scm.com](https://git-scm.com/) and run it. The default options are suitable for most users. This also installs Git Bash, a terminal environment you can use for Git commands.

To verify your installation, open a terminal (Terminal on macOS, PowerShell or Git Bash on Windows) and run:

```bash
git --version
```

### Additional Tools (Project-Dependent)

Depending on what you build with the framework, you may need additional tools. The Sprinter agent will inform you of any requirements when you start a sprint. Common examples include:

- **Node.js** for web applications and JavaScript projects
- **Python** for data science, automation, or backend projects
- **Docker** for containerized applications

You do not need to install these in advance. The agents will guide you through any project-specific setup during the workflow.

---

## Installing OpenCode

OpenCode is the AI coding assistant that powers the agent framework. It provides the chat interface where you interact with the agents and manages the connection to your LLM provider. Unlike some proprietary AI coding tools, OpenCode is open-source and supports multiple LLM providers, giving you flexibility in choosing which AI models to use.

OpenCode consists of two parts: the OpenCode application itself, and a VS Code extension that integrates it into your editor.

### Step 1: Install OpenCode

Visit [opencode.ai](https://opencode.ai) and follow the installation instructions for your operating system:

- **macOS:** Download the installer or use Homebrew
- **Windows:** Download and run the Windows installer

The website provides detailed, up-to-date installation instructions. Follow them to complete the OpenCode installation.

### Step 2: Install the VS Code Extension

Once OpenCode is installed, you need to add the VS Code extension to integrate it into your editor:

1. Open VS Code
2. Click the Extensions icon in the left sidebar (or press `Ctrl+Shift+X` on Windows, `Cmd+Shift+X` on macOS)
3. Search for "OpenCode"
4. Click the **Install** button on the OpenCode extension
5. Wait for the installation to complete and restart VS Code if prompted

### Step 3: Verify the Integration

After both installations are complete, you should see a new OpenCode icon in the VS Code sidebar. Clicking it opens the chat panel where you will interact with the agents.

---

## Configuring Your LLM Provider

OpenCode does not include its own AI model—it connects to external LLM providers. You need to configure access to at least one provider before the agents will work. This section covers the recommended approach.

### GitHub Copilot (Recommended)

GitHub Copilot is the recommended provider for Agile-AI because it offers access to multiple high-quality LLM models through a single subscription, and it integrates seamlessly with VS Code. For academic users, GitHub provides a significant benefit: the **GitHub Education** program offers free Copilot access to students, teachers, and researchers.

**Setting up GitHub Education (for Academics):**

If you have an academic affiliation (student, faculty, or researcher), you can get free access to GitHub Copilot:

1. Visit [education.github.com/pack](https://education.github.com/pack)
2. Click "Get your Pack" and sign in with your GitHub account (create one if needed)
3. Verify your academic status using your institutional email address or other documentation
4. Verification typically takes a few days

Once approved, you will have free access to GitHub Copilot and its available models.

**Installing GitHub Copilot:**

1. In VS Code, open the Extensions panel (`Ctrl+Shift+X` or `Cmd+Shift+X`)
2. Search for "GitHub Copilot"
3. Install both "GitHub Copilot" and "GitHub Copilot Chat" extensions
4. Sign in with your GitHub account when prompted

**Configuring OpenCode to use Copilot:**

1. Open OpenCode settings in VS Code
2. Select GitHub Copilot as your provider
3. Choose your preferred model. For Agile-AI, we recommend:
   - **Claude Sonnet 4** — Excellent balance of capability and speed, works well for all three agents
   - **Gemini 2.5 Pro** — Strong alternative with good reasoning capabilities

The model selection can be changed at any time, and you can even switch models between sessions if you want to compare results.

### Alternative: Direct API Access

If you have direct API access to Anthropic (Claude), OpenAI (GPT-4), or Google (Gemini), you can configure OpenCode to use these providers directly. This approach requires an API key and typically involves usage-based billing.

1. Open VS Code Settings (`Ctrl+,` or `Cmd+,`)
2. Search for "OpenCode"
3. Find the provider configuration section
4. Enter your API key for your chosen provider
5. Select the specific model you want to use

For best results, use capable models such as Claude Sonnet 4, GPT-4o, or Gemini 2.5 Pro. Smaller models may work but could produce lower-quality outputs, particularly in the Architect and Sprinter phases where complex reasoning is required.

---

## Setting Up the Framework

Now that your development environment is ready, you can set up the Agile-AI framework itself.

### Cloning the Repository

Open a terminal and navigate to the directory where you want to create your project. Then clone this repository:

```bash
git clone https://github.com/[username]/agile-ai.git
cd agile-ai
```

Alternatively, you can download the repository as a ZIP file from GitHub and extract it to your desired location.

### Opening the Project in VS Code

Open the cloned directory in VS Code:

- **From Terminal:** Run `code .` in the project directory
- **From VS Code:** Use File → Open Folder and select the `agile-ai` directory

VS Code should automatically recognize the `.opencode` directory and make the agents available.

### Understanding the Agent Configuration

The agents are configured through Markdown files in the `.opencode/agents/` directory. Each agent has:

- A main definition file (e.g., `visionary.md`) that defines the agent's role, constraints, and behavior
- A `commands/` subdirectory containing the start and complete commands

You generally do not need to modify these files. They are pre-configured to work with the framework. However, if you want to customize agent behavior for your specific needs, you can edit these files—they are plain Markdown with YAML frontmatter.

### Verifying the Installation

To confirm everything is working correctly:

1. Open the OpenCode chat panel in VS Code
2. Ensure your LLM provider is connected (you should see a model name in the panel)
3. Type the following command:

```
/visionary-start
```

The Visionary agent should respond with an introduction and begin asking questions about your project. If you see this response, your installation is complete and working.

---

## Project Structure

Understanding the directory structure will help you navigate the framework and know where to find things as you work.

```
agile-ai/
├── .opencode/
│   └── agents/           # Agent definitions (the "brains" of the framework)
│       ├── visionary/    # Phase 1: Requirements gathering
│       ├── architect/    # Phase 2: Technical planning
│       └── sprinter/     # Phase 3: Implementation
│
├── agile/
│   ├── artifacts/        # Where generated documents are stored
│   │   ├── 01_vision/    # Phase 1 outputs
│   │   ├── 02_structure/ # Phase 2 outputs  
│   │   └── 03_work/      # Phase 3 outputs (sprint documentation)
│   ├── templates/        # Templates and examples for each phase
│   └── docs/             # Framework documentation
│
├── results/              # Where generated code is written
│
├── README.md
├── INSTALLATION.md       # This file
└── LICENSE
```

The `agile/artifacts/` directories start empty and fill up as you progress through the workflow. The `results/` directory is where the Sprinter agent writes your actual application code.

---

## Next Steps

With the installation complete, you are ready to begin using the framework. The typical workflow is:

1. **Start Phase 1:** Type `/visionary-start` to begin the requirements interview. The Visionary will ask questions about your project and help you define what you want to build.

2. **Complete Phase 1:** When you are satisfied with the documented requirements, type `/visionary-complete` to generate the Phase 1 artifacts.

3. **Start Phase 2:** Type `/architect-start` to begin technical planning. The Architect will ask about technology preferences and create an implementation plan.

4. **Complete Phase 2:** Type `/architect-complete` to generate the technical documentation and sprint plan.

5. **Start Phase 3:** Type `/sprinter-start` to begin implementation. The Sprinter will work through your sprints, writing code and asking you to test each increment.

6. **Complete Each Sprint:** After testing, type `/sprinter-complete` to commit the working code and move to the next sprint. Repeat until all sprints are complete.

For more detailed information about each phase, see the [Workflow Overview](agile/docs/WORKFLOW.md) and [Agent Roles](agile/docs/ROLES.md) documentation.

---

## Troubleshooting

### "Agent not found" error

This usually means OpenCode cannot find the agent definition files. Verify that:

- You opened the correct directory in VS Code (the one containing `.opencode/`)
- The `.opencode/agents/` directory exists and contains the three agent subdirectories
- You have not accidentally renamed or moved any files

### "Model not available" error

This indicates a problem with your LLM provider configuration. Check that:

- Your API key is correctly entered (if using direct API access)
- Your GitHub Copilot subscription is active (if using Copilot)
- You have selected a valid model in the OpenCode settings

### Slow or unresponsive agent

AI model response times vary depending on server load and your internet connection. If responses are very slow:

- Try a different model (some are faster than others)
- Check your internet connection
- Wait a moment and try again—provider APIs occasionally experience high load

### Getting Help

If you encounter issues not covered in this guide:

- Check the [GitHub Issues](https://github.com/[username]/agile-ai/issues) for known problems and solutions
- Open a new issue describing your problem
- Contact the maintainer at andreas.haja@hs-emden-leer.de
