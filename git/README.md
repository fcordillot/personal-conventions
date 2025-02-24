# GIT conventions
[← Back](../README.md)

## Branches
*   `main`: Production branch. Should only receive merge requests via GitHub or GitLab, not from local GIT CLI. Needs reviews and tests to be merged.
*   `hotfixes`: Branch for emergency bug fixes from production branch.
*   `development`: Main development branch. Guide line for development. NO DIRECT DEVELOPMENT ON THIS BRANCH. Needs reviews to be merged with `main`.
*   `feature/bug/…`: Specific branches created from `development` to dev features, fix bugs, ...

### Merge direction
`feature/bug` → `development` → `preprod` → `main`

## Commit rules
### Syntax

```bash
type(scope): description - version
```

### Types
*   **build**: Build system (npm, webpack, babbel, …)
*   **ci**: Continuous integration (Travis, Circle, BrowserStack, SauceLabs, ...)
*   **db**: Database
*   **docs**: Documentation
*   **feat**: New feature or feature update
*   **fix**: Bug fix
*   **perf**: Performances optimizations and improvements
*   **refactor**: Changes inside code which do not change the way the application or website works
*   **clean**: Files cleaning
*   **test**: Tests
*   **env**: Environment
*   **upgrade**: Module or dependency updates
*   **update**: other updates

### Scope
Define the project part which is affected by the commit.

<u><i>Examples:</i></u>
```bash
update(app) # The update concerns the application globaly
update(auth) # The update concerns the Authentication module
update(auth & blog) # Modifications have been made on both Authentication and Blog modules
```

**⚠ ATTENTION**: If a commit concerns **more than 3 modules**, the scope would be `app`.

### Description
A short description about the changes have been made.

The imperative present should be used to describe the changes. The past or present tense should **NOT be used**.
<br />
<u><i>For example:</i></u>

```bash
update(auth): change ... # NOT "changed" or "changes"
```
The decription should start with lowercase and end without dot.

### Version
The project version concerned by the changes. For example: 4.3.12

## Commit examples
```bash
git commit -m “feat(account): graphical review - v4.4.62”
```