<!-- omit from toc -->
# Visual Studio Code

Visual Studio Code (VS Code) is a free and open-source code editor developed by Microsoft. It's designed to provide a lightweight yet powerful environment for software development across a wide range of programming languages. VS Code is known for its simplicity, high performance, and extensibility, making it a popular choice among developers of all skill levels.

Start out by exploring the site and then downloading the client:\
<https://code.visualstudio.com/>

You may also access and use a lightweight version of the VS Code in your browser:\
<https://vscode.dev/>

VS Code is an extremely powerful tool with a lot of features. I'll simply scratch the surface with some quality of life tips and extensions.

<!-- omit from toc -->
## Content

- [Recommended Extensions](#recommended-extensions)
- [Quality of Life Tips](#quality-of-life-tips)
  - [How to change the default terminal profile in VS Code](#how-to-change-the-default-terminal-profile-in-vs-code)
  - [How to launch VS Code from your terminal of choice](#how-to-launch-vs-code-from-your-terminal-of-choice)

## Recommended Extensions

SpellChecker
<https://www.youtube.com/watch?v=ZxNnOjWetH4>

## Quality of Life Tips

### How to change the default terminal profile in VS Code

<https://www.w3schools.io/editor/vscode-change-default-terminal/>

### How to launch VS Code from your terminal of choice

 If you want to run VS Code from the terminal by simply typing 'code', VS Code has a command, Shell Command: Install 'code' command in PATH, to add 'code' to your $PATH variable list.

After installation, launch VS Code. Now open the Command Palette (`⇧+⌘+P`) and type `shell command` to find the `Shell Command: Install 'code' command in PATH` command.

After executing the command, restart the terminal for the new $PATH value to take effect. You'll be able to simply type `code .` in any folder to start editing files in that folder.

```bash
tldr code
code -n .
code -a .
```

**[- Back to Top -](#content)**

---

**[- Notes / NetDevOps -](../..)**

**[- Notes / Home -](../../..)**
