# Git Conventional Commits: Platform Engineering Standard

## Architecture / Rationale

A deterministic version control history is mandatory for Platform Engineering and Documentation as Code (DaC). Utilizing a strict Conventional Commits standard eliminates decision fatigue, enables automated semantic versioning, and allows CI/CD pipelines to parse repository changelogs programmatically.

System state mutations (commits) must be atomic. You must target a single logical change per execution. Mixing unrelated domain updates in a single commit corrupts the repository's audit trail.

## Reference Tables

### Core Commit Anatomy

**Standard Syntax:** `<type>(<scope>): <imperative subject>`
**Valid Example:** `feat(ops): add docker network audit script`
**Invalid Example:** `added some docker stuff and fixed typos`

### Primary Types (The DaC Standard)

| Type | Target / Domain | Operational Use Case |
| :--- | :--- | :--- |
| `docs` | Markdown / Text | Theoretical knowledge, readmes, and handbook content updates. |
| `feat` | Executable Code | Introduction of new Bash scripts, SQL migrations, or Docker configurations. |
| `fix` | Error Resolution | Repairing broken scripts, runtime errors, or correcting critical typos in documentation. |
| `refactor` | Structure | Topology changes, moving directories, or purging deprecated files without altering functionality. |
| `chore` | Repo Infrastructure| Maintenance tasks invisible to the final product build (e.g., `.gitignore`, `LICENSE`, `.readmeAI`). |

### Extended Types (CI/CD & Operations)

| Type | Target / Domain | Operational Use Case |
| :--- | :--- | :--- |
| `ci` | Pipelines | Modifications to GitHub Actions, GitLab CI, or deployment workflow automation. |
| `test` | Validation | Adding or modifying unit tests (e.g., `bats` for bash scripts, `pytest` for Python data pipelines). |
| `perf` | Optimization | Code changes that specifically improve compute or database execution time (e.g., SQL indexing). |
| `revert` | State Rollback | Reverting a previous commit to restore platform stability after an incident. |
| `style` | Formatting | Fixing trailing spaces, markdown linting, or code formatting (zero logic changes). |

## Operational Commands

```bash
# 1. Audit current working directory state before staging
git status

# 2. Stage specific atomic changes (Do not use 'git add .' blindly in production)
git add ./02-Development/sql-guide/03-joins/

# 3. Execute canonical single-line commit
git commit -m "docs(sql): document execution plans for inner joins"

# 4. Execute multi-line commit for complex platform changes (Provides context)
git commit -m "refactor(struct): purge legacy sql-basics directory" -m "Remove redundant flat files to enforce strict hierarchical DaC standard."

# 5. Audit commit history tree to verify semantic compliance
git log --oneline --graph --decorate -n 10
```
