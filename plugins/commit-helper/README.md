# commit-helper

A minimal Claude plugin with one skill, `commit-message`, which proposes a
[Conventional Commits](https://www.conventionalcommits.org/) message for your staged changes.

## Usage

Stage your changes, then ask Claude: "write a commit message for my staged changes",
or invoke the skill directly as `/commit-helper:commit-message`.

## Install

```
/plugin marketplace add OleksandrMartynov/claude-plugins
/plugin install commit-helper@martynov-plugins
```
