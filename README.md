# Ghidra CLI

Command Line Interface for Ghidra so you can move _**fast**_

## Why?
Isn't it annoying:
1. Opening Ghidra
2. Waiting for it to load
3. Creating a new project, awkwardly navigating to your current directory
4. Finding and importing your binary
5. Waiting for it to analyze

**and ONLY NOW** can you start your reversing.

_With **ghidra-cli**, all you do is_
```bash
ghidra-cli -n -i ./my_binary
```
The Ghidra project will be created, the binary imported, and analyzed for you!

## Installation
Put the [ghidra-cli](./ghidra-cli) script somewhere in your `$PATH` and enjoy!

> [!NOTE]
> Make sure the `GHIDRA_PATH` inside the script is the path to where your Ghidra is installed

## Examples
Create a new temporary project (in /tmp/) and import+analyze ./chal:
```bash
ghidra-cli -n -i ./chal
```
Create a new empty project in the current directory with the name 'ghidra'
```bash
ghidra-cli -n -d . --name ghidra
```
Open an existing ghidra project called my_project:
```bash
ghidra-cli ./ghidra.gpr
```

## Usage
```
Usage: ghidra-cli [-h | --help] [project]
       ghidra-cli (-n | --new-project) [(-d <dir>) (--name <name>)] (-i (<directory>|<file>))...

  -h, --help                          Show this screen.
  -n, --new-project                   Create a new project.
  -d, --project-dir <dir>             Directory where to create the new project. [default: /tmp]
  --name <name>                       The name of the new project.
  -i, --import (<directory>|<file>)   The file/directory of files to import into the new project. May be specified multiple times.
```
