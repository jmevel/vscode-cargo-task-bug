# README

This is a minimal reproduction of an issue when using Visual Studio Code tasks to execute `cargo` commands (for building the project or whatever).

This project has simply been created with `cargo new vscode-cargo-task-bug`, I then executed the command `Tasks: Configure Default Build Task` from the command palette and replaced the default `tasks.json` template to the one you can see (I didn't copy paste anything, I typed everything so be sure there's no weird character hidden in the file).

As you can see, when launching the project with Visual Studio Code, the task runner isn't able to completely parse the `tasks.json` file and an error popup occurred showing the following error

>Error: The cargo task detection didn't contribute a task for the following configuration:
{
    "label": "rust: cargo version",
    "type": "cargo",
    "command": "version"
}
The task will be ignored.
Error: The cargo task detection didn't contribute a task for the following configuration:
{
    "label": "rust: cargo build",
    "type": "cargo",
    "command": "build"
}
The task will be ignored.

As a workaround, one can replace the `cargo` command by a `shell` as shown in the `tasks.json` file.
These commands are successfully parsed when launching VS Code and can be executed from the `Task Runner` without any problem.
