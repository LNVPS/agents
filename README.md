# Shared Agent Guidelines

A reusable set of coding agent guidelines that can be shared across multiple repositories using git submodules.

## Structure

```
.
├── AGENTS.md.template      # Template for your project's AGENTS.md
├── bug-fixes.md
├── coverage.md
├── incremental-work.md
└── README.md
```

## Bootstrap: Adding to Your Project

### 1. Add as a git submodule

```bash
cd your-project
git submodule add https://github.com/LNVPS/agents.git agents
git submodule update --init --recursive
```

This places the submodule at `agents/`, so paths become `agents/coverage.md`.

### 2. Create your project's AGENTS.md

Copy the template and customize it:

```bash
cp agents/AGENTS.md.template AGENTS.md
```

Edit `AGENTS.md` to:
- Replace `[PROJECT_NAME]` with your project name
- Add your project-specific docs to the table
- Add any active work files

### 3. Create work/ directory

```bash
mkdir -p work
```

## Updating the Submodule

To pull updates from the shared repo:

```bash
cd agents
git pull origin main
cd ..
git add agents
git commit -m "Update agents submodule"
```

## Generic Guidelines

The generic guidelines cover:

- **bug-fixes.md** - Regression test requirements for bug fixes
- **coverage.md** - 100% function coverage policy for new/modified code  
- **incremental-work.md** - Work file format for tracking multi-session tasks

## Contributing

To add new generic guidelines that apply across all projects:

1. Add the doc to this repo
2. Update `AGENTS.md.template` to reference it
3. Update this README
