# Hierarchical Memory System: Developer Guide

## Introduction

This guide outlines the development practices, code standards, and workflow expectations for all contributors to the Hierarchical Memory System project. Adherence to these standards is mandatory for all contributions.

## Development Workflow

### Task Assignment

- All development tasks are assigned exclusively through GitHub Issues
- Engineers must not self-assign tasks without explicit approval
- Task descriptions in GitHub Issues are considered definitive requirements
- All feedback and suggestions in issues/PRs must be implemented unconditionally

### Pair Programming Model

- All development is conducted via pair programming
- Each engineer is paired with a mentor through a chat interface
- The mentor will guide implementation decisions and review approach
- Communication should be maintained throughout the development process

### Test-Driven Development

- **Every** feature implementation must begin with a test
- The workflow sequence is strictly enforced:
  1. Write minimal failing test that verifies the required behavior
  2. Implement minimal code to make the test pass
  3. Refactor while maintaining passing tests
  4. Repeat for next requirement
- No code will be accepted without corresponding tests
- Target test coverage is 90%+ for all modules

## Code Standards

### Type Annotations

- **All** Python code must use complete type annotations
- Mypy validation is required for every commit
- Strict mode is enabled (`--strict` flag)
- No `# type: ignore` comments without explicit approval and justification
- Use the most specific types possible (avoid `Any` where feasible)

### Error Handling

- We follow a **fail fast** approach for configuration/setup errors
- Be explicit about preconditions and validate them early
- Raise specific, descriptive exceptions for configuration errors
- Do not attempt to infer or repair misconfiguration silently
- Runtime errors should be handled gracefully with appropriate logging

### Import Standards

- All imports must be placed at the top of the file
- No conditional imports allowed
- Imports must be organized in the following groups, separated by blank lines:
  1. Standard library imports
  2. Third-party library imports
  3. Application-specific imports
- Within each group, use alphabetical ordering
- Use absolute imports throughout the codebase

### Code Style

- All code must conform to PEP 8 standards
- Maximum line length is 88 characters (Black formatter standard)
- Use meaningful variable, function, and class names
- Limit function length to maximum 50 lines
- Black and isort are used for formatting (configuration in pyproject.toml)

## Documentation Requirements

### Code Documentation

- All modules, classes, methods, and functions must include docstrings
- Docstrings must follow Google style format
- Complex logic must include inline comments explaining the rationale
- Public APIs require comprehensive documentation with examples

### API Documentation

- API documentation is auto-generated from docstrings
- All public interfaces must be properly documented for auto-generation
- Include usage examples in docstrings for all public methods
- Document parameter types, return values, and exceptions

### Architecture Documentation

- Major components require architecture documentation
- Document component interactions and dependencies
- Include diagrams where appropriate (using PlantUML)
- Update architecture documentation when making significant changes

## Bug Management

- All bugs must be tracked in GitHub Issues
- When discovering a bug during development:
  1. Create a new issue or sub-issue linked to the original task
  2. Include reproduction steps and relevant context
  3. Do NOT attempt to fix bugs unless specifically assigned
- Bug fixes require their own dedicated PRs
- Include test cases that reproduce the bug

## Pull Request Process

- PRs should reference the corresponding issue number
- Provide clear descriptions of implementation approach
- Include screenshots or demos for UI/UX changes
- Address all review comments promptly
- Maintain CI/CD pipeline integrity
- Keep PRs focused on a single feature/issue

## Development Environment

- Use the provided dev container or virtual environment
- Ensure all linting and type checking passes locally before submitting
- Pre-commit hooks are configured to enforce standards
- Automated tests must pass in the local environment

## Commit Standards

- Use semantic commit messages (feat, fix, docs, style, refactor, test, chore)
- Include issue number in commit message
- Keep commits focused and atomic
- Squash WIP commits before PR submission

## Getting Help

- Technical questions should be asked in the issue thread
- Architecture questions should be directed to tech leads
- Process questions can be addressed to project managers
- Use the development Slack channel for general discussions

Remember that strict adherence to these standards ensures a maintainable, high-quality codebase and smooth collaboration between team members.
