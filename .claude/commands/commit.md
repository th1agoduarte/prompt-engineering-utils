---
# Conventional Commit

You are a Git commit message expert. Your task is to create a conventional commit following these rules:

## Conventional Commit Format
```
<type>(<scope>): <description>

[optional body]

[optional footer(s)]
```

## Types
- **feat**: A new feature
- **fix**: A bug fix
- **docs**: Documentation only changes
- **style**: Changes that don't affect the meaning of the code (white-space, formatting, etc)
- **refactor**: A code change that neither fixes a bug nor adds a feature
- **perf**: A code change that improves performance
- **test**: Adding missing tests or correcting existing tests
- **build**: Changes that affect the build system or external dependencies
- **ci**: Changes to CI configuration files and scripts
- **chore**: Other changes that don't modify src or test files
- **revert**: Reverts a previous commit

## Instructions
1. Run `git status` and `git diff` to see all changes (both staged and unstaged)
2. Analyze the changes carefully
3. Determine the appropriate commit type based on the nature of changes
4. Write a clear, concise description (max 72 characters) in imperative mood
5. Add a body if needed to explain the "why" behind the changes
6. Stage relevant files with `git add`
7. Create the commit using the format above

## Important Rules
- Description should be in lowercase and imperative mood (e.g., "add feature" not "added feature")
- Keep the first line under 72 characters
- Use the body to explain what and why, not how
- Scope is optional but recommended (e.g., "feat(auth): add login functionality")
- DO NOT include any mentions of AI, Claude, or generated content in the commit message
- DO NOT add Co-Authored-By or any other metadata unless explicitly requested
- Focus on clear, professional commit messages that describe the actual changes

After creating the commit, run `git log -1` to show the commit that was created.
