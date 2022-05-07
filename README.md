# README

This is a minimal reproduction of an issue when using Visual Studio Code tasks to execute `cargo` commands (for building the project or whatever).

This project has simply been created with `cargo new vscode-cargo-task-bug`, I then executed the command `Tasks: Configure Default Build Task` from the command palette and replaced the default `tasks.json` template to the one you can see (I didn't copy paste anything, I typed everything so be sure there's no weird character hidden in the file).

As a workaround, one can replace the `cargo` command by a `shell` as shown in the `tasks.json` file.
