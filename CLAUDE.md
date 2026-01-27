# CLAUDE.md - AI Assistant Guide for TER-revamp

> This file provides context and guidelines for AI assistants working with this codebase.
> Last updated: 2026-01-27

## Project Overview

**Repository:** TER-revamp
**Status:** New/Initializing
**Description:** [TODO: Add project description as the codebase develops]

This is a newly initialized repository. As the project develops, this document should be updated to reflect the actual codebase structure, conventions, and workflows.

---

## Quick Reference

### Common Commands

```bash
# [TODO: Add build commands]
# npm run build
# make build

# [TODO: Add test commands]
# npm test
# pytest

# [TODO: Add development server commands]
# npm run dev
# python manage.py runserver

# [TODO: Add linting/formatting commands]
# npm run lint
# black . && isort .
```

### Key Files to Know

| File/Directory | Purpose |
|---------------|---------|
| `CLAUDE.md` | AI assistant guidelines (this file) |
| `README.md` | [TODO: Create project documentation] |
| `src/` | [TODO: Main source code] |
| `tests/` | [TODO: Test files] |

---

## Codebase Structure

```
TER-revamp/
├── CLAUDE.md           # AI assistant guidelines
├── README.md           # [TODO] Project documentation
├── src/                # [TODO] Main source code
├── tests/              # [TODO] Test files
├── docs/               # [TODO] Additional documentation
└── [config files]      # [TODO] Configuration files
```

> **Note:** Update this structure as the project develops.

---

## Technology Stack

[TODO: Document the technology stack as it's established]

- **Language:** [e.g., TypeScript, Python, Go]
- **Framework:** [e.g., React, Django, Express]
- **Database:** [e.g., PostgreSQL, MongoDB]
- **Build System:** [e.g., Webpack, Vite, Make]
- **Package Manager:** [e.g., npm, yarn, pip, poetry]
- **Testing:** [e.g., Jest, pytest, Go test]

---

## Development Workflow

### Setting Up the Environment

```bash
# [TODO: Add setup instructions]
# 1. Clone the repository
git clone <repository-url>
cd TER-revamp

# 2. Install dependencies
# npm install
# pip install -r requirements.txt

# 3. Configure environment
# cp .env.example .env

# 4. Start development
# npm run dev
```

### Branch Naming Convention

- `main` or `master` - Production-ready code
- `develop` - Integration branch for features
- `feature/<description>` - New features
- `bugfix/<description>` - Bug fixes
- `hotfix/<description>` - Urgent production fixes
- `claude/<session-id>` - AI assistant working branches

### Commit Message Format

Follow conventional commits:

```
<type>(<scope>): <description>

[optional body]

[optional footer]
```

Types: `feat`, `fix`, `docs`, `style`, `refactor`, `test`, `chore`

Examples:
```
feat(auth): add OAuth2 login support
fix(api): handle null response in user endpoint
docs: update CLAUDE.md with new conventions
```

---

## Code Conventions

### General Principles

1. **Keep it simple** - Avoid over-engineering; implement only what's needed
2. **Be consistent** - Follow existing patterns in the codebase
3. **Write tests** - Add tests for new functionality
4. **Document intent** - Comment the "why", not the "what"
5. **Security first** - Never commit secrets; validate inputs

### Style Guidelines

[TODO: Add language-specific style guidelines]

```
# Example for TypeScript/JavaScript:
- Use TypeScript strict mode
- Prefer `const` over `let`
- Use meaningful variable names
- Max line length: 100 characters

# Example for Python:
- Follow PEP 8
- Use type hints
- Max line length: 88 characters (Black default)
```

---

## Testing Guidelines

### Running Tests

```bash
# [TODO: Add test commands]
# Run all tests
# npm test

# Run specific test file
# npm test -- path/to/test.ts

# Run with coverage
# npm test -- --coverage
```

### Writing Tests

[TODO: Document testing patterns and expectations]

- Unit tests for business logic
- Integration tests for API endpoints
- E2E tests for critical user flows
- Aim for meaningful coverage, not 100%

---

## Architecture Notes

[TODO: Document key architectural decisions as they're made]

### Key Patterns

- [e.g., Repository pattern for data access]
- [e.g., Service layer for business logic]
- [e.g., Event-driven communication]

### Important Decisions

| Decision | Rationale | Date |
|----------|-----------|------|
| [TODO] | [TODO] | [TODO] |

---

## Environment Configuration

### Required Environment Variables

[TODO: Document required environment variables]

```bash
# .env.example
# DATABASE_URL=postgresql://localhost:5432/ter
# API_KEY=your-api-key-here
# NODE_ENV=development
```

### Configuration Files

| File | Purpose |
|------|---------|
| `.env` | Local environment variables (git-ignored) |
| `.env.example` | Template for environment setup |
| [TODO: Add other config files] | [TODO] |

---

## AI Assistant Guidelines

### When Working on This Codebase

1. **Read before writing** - Always understand existing code before modifying
2. **Use TodoWrite** - Track tasks and progress for complex work
3. **Make incremental changes** - Small, focused commits are preferred
4. **Test your changes** - Run tests before committing
5. **Update documentation** - Keep CLAUDE.md and README.md current

### Things to Avoid

- Don't add features beyond what's requested
- Don't introduce new dependencies without justification
- Don't commit sensitive data (API keys, passwords)
- Don't skip tests or disable linting
- Don't make breaking changes without documentation

### Helpful Patterns

When exploring this codebase:
```bash
# Find files by pattern
# Use Glob tool with patterns like "**/*.ts"

# Search for code patterns
# Use Grep tool to search content

# Understand structure
# Use Task tool with Explore agent for complex exploration
```

---

## Troubleshooting

### Common Issues

[TODO: Document common issues and solutions as they arise]

| Issue | Solution |
|-------|----------|
| [TODO] | [TODO] |

### Getting Help

- Check existing documentation
- Search closed issues/PRs
- Ask in project communication channels

---

## Changelog

| Date | Changes |
|------|---------|
| 2026-01-27 | Initial CLAUDE.md created for empty repository |

---

## Notes

This CLAUDE.md was created when the repository was empty. As the project develops:

1. Replace all `[TODO]` placeholders with actual information
2. Update the codebase structure section
3. Document the actual technology stack
4. Add specific commands for building, testing, and running
5. Document architectural decisions as they're made
6. Add troubleshooting entries for common issues

Keep this file up-to-date as the single source of truth for AI assistants working with this codebase.
