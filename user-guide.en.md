# GoDojo Author CLI User Guide

Complete guide for using the CLI to create educational content.

## Installation

### Pre-built Binaries

Download the appropriate binary for your operating system:

- **Windows**: `godojo-author-windows-amd64.exe`
- **macOS Intel**: `godojo-author-macos-intel-amd64`
- **macOS Apple Silicon**: `godojo-author-macos-silicon-arm64`
- **Linux**: `godojo-author-linux-amd64`

```bash
# Make the file executable (macOS/Linux)
chmod +x godojo-author

# Test functionality
./godojo-author --version
```

### Build from Source

```bash
# Clone and build
git clone <repository-url>
cd godojo_cli
make build

# Ready binary will be in builds/dev/
./builds/dev/godojo-author --version
```

## Initial Setup

### Author Profile Initialization

The `init` command creates your author profile and can be executed in any directory:

```bash
./godojo-author init
```

You will be asked the following questions:

1. **Full Name** — your name for content attribution
2. **Email** — contact information
3. **GitHub username** (optional) — for linking to your profile
4. **Interface Language** — Russian (ru) or English (en)
5. **Content Languages** — languages you create materials in
6. **Areas of Expertise** — your Go specializations

After completion, an `author.config.json` file will be created with your settings.

### Environment Check

Before starting work, ensure you're in the correct repository:

```bash
./godojo-author check structure
```

This command checks for all necessary directories and files:
- `content/` — for educational content
- `templates/` — for templates
- `_meta/` — for metadata
- `docs/` — for documentation
- `.github/` — for GitHub configuration

## Content Creation

### Creating a New Topic

Main command for creating educational content:

```bash
./godojo-author create topic
```

#### Topic Creation Process

1. **Category Selection** — from the list of allowed categories:
   - `basics` — language fundamentals
   - `concurrency` — concurrent programming
   - `web` — web development
   - `database` — database work
   - `testing` — testing
   - `production` — production-ready code
   - `performance` — performance optimization
   - `frameworks` — frameworks and libraries
   - `security` — security
   - and others...

2. **Module Number** — number from 1 to 79, determining order in the course

3. **Topic Title** — brief, descriptive title

4. **Topic Slug** — automatically generated from the title

#### Creation Result

After successful topic creation:

```
content/
└── {selected-category}/
    └── {module-number:02d}-{topic-slug}/
        └── topic.md
```

The `topic.md` file will contain:
- Frontmatter with metadata
- Structured sections for content
- Template stubs for filling

### Creating a New Chapter

```bash
./godojo-author create chapter
```

*Feature is in development*

## Profile Management

### Status View

```bash
./godojo-author status
```

Shows:
- Your profile information
- Created content statistics
- Language and expertise settings
- Recent activity

### Configuration Management

```bash
./godojo-author config
```

*Feature is in development*

Will allow:
- Changing personal information
- Updating areas of expertise
- Configuring language preferences

## Validation and Quality Control

### Content Validation

```bash
./godojo-author validate
```

*Feature is in development*

Will check:
- **Structural validation** — frontmatter correctness, required fields
- **Quality validation** — minimum 800 words, 3 code examples, 2 exercises
- **Code validation** — compilation of all Go examples
- **Standards compliance** — section structure, formatting

### View Created Content

```bash
./godojo-author list
```

*Feature is in development*

Will show:
- List of all created topics
- Validation status of each topic
- Statistics by categories
- Content completion progress

## Topic Structure

### Required Sections

Each topic must contain:

1. **Frontmatter** — metadata in YAML format
2. **Description** — brief introduction to the topic (1-2 paragraphs)
3. **Theory** — main theoretical material
4. **Examples** — practical code examples (minimum 3)
5. **Exercises** — assignments for independent work (minimum 2)
6. **Summary** — brief conclusions and key points
7. **Additional Resources** — links to supplementary materials

### Quality Requirements

- **Text Volume** — minimum 800 words
- **Code Examples** — minimum 3 working examples
- **Exercises** — minimum 2 practical assignments
- **Compilation** — all Go code must compile without errors
- **Formatting** — following unified markup style

### Frontmatter

Example of correct frontmatter:

```yaml
---
title: "Working with Channels in Go"
description: "Learning the basics of working with channels for organizing interaction between goroutines"
author: "Your Name"
category: "concurrency"
module: 15
level: "intermediate"
estimated_time: "45-60 minutes"
tags: ["channels", "goroutines", "concurrency"]
prerequisites: ["basics", "goroutines"]
---
```

## Author Workflow

### Daily Work

1. **Planning** — determine topics to create
2. **Creation** — use `create topic` for new topics
3. **Content** — fill created templates with content
4. **Verification** — validate quality through `validate`
5. **Tracking** — monitor progress through `status`

### Efficiency Tips

- **Create topics in batches** — easier to get into rhythm
- **Use templates** — adapt them to your style
- **Monitor statistics** — motivates and shows progress
- **Save in Git** — maintain change history
- **Validate regularly** — fix errors early

### Personalization

#### Template Configuration

Create your own templates in the `templates/` directory:

```bash
# Copy base template
cp templates/topic.md templates/my-topic.md

# Edit to your needs
```

#### Command Aliases

For convenience, add to `~/.bashrc` or `~/.zshrc`:

```bash
alias ga='./godojo-author'
alias gat='./godojo-author create topic'
alias gas='./godojo-author status'
alias gav='./godojo-author validate'
```

## Troubleshooting

### Common Errors

**"Author configuration not found"**
```bash
# Solution: initialize profile
./godojo-author init
```

**"Incorrect repository structure"**
```bash
# Solution: check structure
./godojo-author check structure
# Make sure you're in the correct directory
```

**"Insufficient write permissions"**
```bash
# Solution: check access rights
chmod +x godojo-author
# Make sure you have write permissions to the directory
```

### Configuration Recovery

If the `author.config.json` file is corrupted:

```bash
# Create backup
cp author.config.json author.config.json.backup

# Recreate configuration
./godojo-author init
```

### Diagnostics

For detailed error information:

```bash
# Enable debug mode
export GODOJO_DEBUG=true
./godojo-author <command>
```

## Editor Integration

### VS Code

For convenient Markdown work:

1. Install extensions:
   - Markdown All in One
   - Code Spell Checker
   - YAML

2. Configure auto-formatting:
```json
{
  "markdown.extension.toc.levels": "2..6",
  "markdown.extension.completion.root": "content/"
}
```

### Other Editors

- **Typora** — excellent WYSIWYG Markdown editor
- **Obsidian** — for linking topics together
- **Zettlr** — academic editor with YAML frontmatter support

## Content Writing Tips

### Material Structure

1. **Introduction** — motivate studying the topic
2. **Basics** — explain key concepts
3. **Examples** — demonstrate practical application
4. **Nuances** — reveal gotchas
5. **Conclusion** — summarize and give development directions

### Quality Code Examples

- **Start simple** — from basic concepts to complex
- **Comment code** — explain non-obvious parts
- **Show output** — include execution results
- **Fix errors** — demonstrate correct solutions

### Effective Exercises

- **Difficulty gradation** — from simple to complex
- **Practical value** — tasks from real development
- **Clear formulations** — understandable conditions and expected results
- **Hints and solutions** — help for independent solving

---

This guide will help you effectively use GoDojo Author CLI to create quality educational content. If you have questions, contact the GoDojo team or study additional documentation in the project repository.