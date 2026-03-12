# Getting Started with YOU-DRIVE-SOP

Welcome to the **YOU-DRIVE-SOP** framework. This guide will walk you through setting up your first Foundry and Workshop.

## Step 1: Set Up the Foundry (Mother-Base)

The **Foundry** is your central knowledge repository. It stores the skills and code patterns that all your projects will share.

1. **Clone the Template**:
   ```bash
   git clone https://github.com/your-repo/YOU-DRIVE-SOP.git my-foundry
   cd my-foundry
   ```

2. **Initialize the Foundry**:
   ```bash
   activate_skill foundry-initializing
   ```
   *This creates the necessary directory structure and global standards.*

## Step 2: Set Up a Workshop (Sub-Project)

A **Workshop** is any project where you actually write code. It "links" to the Foundry to access its intelligence.

1. **Enter your project directory**:
   ```bash
   cd /path/to/your/existing-project
   ```

2. **Link to the Foundry**:
   ```bash
   gemini skills link /absolute/path/to/my-foundry/.gemini/skills --scope workspace --consent
   ```

3. **Initialize the Workshop**:
   ```bash
   activate_skill workshop-initializing
   ```
   *This establishes the link, identifies your tech stack, and injects the Global Standard.*

## Step 3: Your First Development Loop

Now that your Workshop is connected, follow the **YOU-DRIVE-SOP** loop for every task:

1. **Propose a Change**:
   ```bash
   /opsx:propose my-new-feature
   ```
   *AI will analyze the requirement against the Foundry's patterns.*

2. **Implement with TDD**:
   ```bash
   /opsx:apply
   ```
   *Write tests first, then decouple logic from UI.*

3. **Distill Assets**:
   Before finishing, AI will ask to harvest generic logic.
   ```bash
   activate_skill meta-distiller
   ```

4. **Archive & Contribute**:
   ```bash
   /opsx:archive
   ```
   *The task is finished, and your Foundry is now smarter.*

---

## 🛡️ Best Practices

- **Never Hardcode Paths**: Always let the framework discover the Foundry root.
- **Trust but Verify**: Use the Staging area (`.gemini/distill_stage/`) to review assets before they enter the Foundry.
- **Stay Safe**: Keep your Workshop under Git control to enable auto-backups and rollbacks.

*Happy Driving!*
