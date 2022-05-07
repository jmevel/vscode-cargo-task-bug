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

## Additional information

VS Code:
>Version: 1.67.0 (user setup)
Commit: 57fd6d0195bb9b9d1b49f6da5db789060795de47
Date: 2022-05-04T12:06:02.889Z
Electron: 17.4.1
Chromium: 98.0.4758.141
Node.js: 16.13.0
V8: 9.8.177.13-electron.0
OS: Windows_NT x64 10.0.22000

Cargo:
>cargo 1.60.0 (d1fd9fe2c 2022-03-01)
release: 1.60.0
commit-hash: d1fd9fe2c40a1a56af9132b5c92ab963ac7ae422
commit-date: 2022-03-01
host: x86_64-pc-windows-msvc
libgit2: 1.3.0 (sys:0.13.23 vendored)
libcurl: 7.80.0-DEV (sys:0.4.51+curl-7.80.0 vendored ssl:Schannel)
os: Windows 10.0.22000 (Windows 10 Pro) [64-bit]

rustc: `1.60.0 (7737e0b5c 2022-04-04)`
