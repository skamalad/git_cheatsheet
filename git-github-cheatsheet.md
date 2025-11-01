# Ultimate Git & GitHub Terminal Cheat Sheet

## 🔑 Legend
- 🔵 **Offline Operations** - Can be performed without internet connection
- 🌐 **Online Operations** - Requires internet connection
- 🟣 **GitHub CLI** - Operations using the GitHub CLI
- ⚡ **Pro Tip** - Advanced/efficient workflow suggestion

## 🛠️ Setup and Configuration

### Initial Setup
- 🔵 `git --version` - Check installed Git version
- 🔵 `git config --global user.name "Your Name"` - Set username
- 🔵 `git config --global user.email "your.email@example.com"` - Set email
- 🔵 `git config --global core.editor "vim"` - Set default editor (vim, nano, etc.)
- 🔵 `git config --global init.defaultBranch main` - Set default branch name
- 🔵 `git config --global color.ui auto` - Enable colorized output

### View Configuration
- 🔵 `git config --list` - Show all settings
- 🔵 `git config user.name` - Show specific setting

### Authentication
- 🔵 `ssh-keygen -t ed25519 -C "your.email@example.com"` - Generate SSH key
- 🌐 Add SSH key to GitHub account via website
- 🌐 `ssh -T git@github.com` - Verify SSH connection

## 📂 Repository Operations

### Creating Repositories
- 🔵 `git init [project-name]` - Create new local repository
- 🌐 `git clone [url]` - Clone a repository
- 🌐 `git clone [url] --depth=1` - Clone with limited history (shallow clone)
- 🌐 `git clone [url] [folder-name]` - Clone into specific folder

### Status & Information
- 🔵 `git status` - Show modified files
- 🔵 `git log` - Show commit history
- 🔵 `git log --oneline` - Compact history view
- 🔵 `git log --graph --oneline --all` - Visual commit history
- 🔵 `git show [commit]` - Show details of specific commit
- 🔵 `git diff` - Show unstaged changes
- 🔵 `git diff --staged` - Show staged changes
- 🔵 `git blame [file]` - Show who changed each line in file

## 💾 Basic Workflow (Offline Operations)

### Tracking Changes
- 🔵 `git add [file]` - Stage specific file
- 🔵 `git add .` - Stage all changed files
- 🔵 `git add -p` - Interactively stage portions of files
- 🔵 `git rm [file]` - Remove file and stage deletion
- 🔵 `git mv [old-path] [new-path]` - Move file and stage move

### Committing
- 🔵 `git commit -m "Descriptive message"` - Commit staged changes
- 🔵 `git commit -a -m "message"` - Stage all tracked files and commit
- 🔵 `git commit --amend` - Modify the last commit
- ⚡ `git commit --amend --no-edit` - Add to last commit without changing message

### Undoing Changes
- 🔵 `git restore [file]` - Discard changes in working directory
- 🔵 `git restore --staged [file]` - Unstage file
- 🔵 `git reset [commit]` - Undo commits but preserve changes
- 🔵 `git reset --hard [commit]` - Discard all history and changes back to specified commit
- 🔵 `git revert [commit]` - Create new commit that undoes changes from specified commit

## 🌿 Branching and Merging (Primarily Offline)

### Branch Management
- 🔵 `git branch` - List all local branches
- 🔵 `git branch -a` - List all branches (local and remote)
- 🔵 `git branch [branch-name]` - Create new branch
- 🔵 `git branch -d [branch-name]` - Delete branch
- 🔵 `git branch -m [old-name] [new-name]` - Rename branch
- 🔵 `git checkout [branch-name]` - Switch to branch
- 🔵 `git checkout -b [branch-name]` - Create and switch to branch
- 🔵 `git switch [branch-name]` - Switch to branch (Git 2.23+)
- 🔵 `git switch -c [branch-name]` - Create and switch to branch (Git 2.23+)

### Merging
- 🔵 `git merge [branch]` - Merge branch into current branch
- 🔵 `git merge --no-ff [branch]` - Create merge commit even if fast-forward is possible
- 🔵 `git merge --abort` - Abort merge in case of conflicts

### Rebasing
- 🔵 `git rebase [branch]` - Reapply commits on top of another branch
- 🔵 `git rebase -i HEAD~[n]` - Interactive rebase for last n commits
- 🔵 `git rebase --abort` - Abort rebase
- 🔵 `git rebase --continue` - Continue rebase after resolving conflicts

## 🌐 Remote Operations (GitHub)

### Remote Management
- 🌐 `git remote -v` - List all remotes
- 🌐 `git remote add [name] [url]` - Add remote
- 🌐 `git remote rename [old-name] [new-name]` - Rename remote
- 🌐 `git remote remove [name]` - Remove remote
- 🌐 `git remote set-url [name] [url]` - Change remote URL

### Syncing with Remotes
- 🌐 `git fetch [remote]` - Download objects and refs from remote
- 🌐 `git fetch --all` - Fetch from all remotes
- 🌐 `git pull` - Fetch and merge changes
- 🌐 `git pull --rebase` - Fetch and rebase changes (avoids merge commits)
- 🌐 `git push [remote] [branch]` - Push local branch to remote
- 🌐 `git push -u [remote] [branch]` - Push and set upstream
- 🌐 `git push --force` - Force push (use with caution!)
- ⚡ `git push --force-with-lease` - Safer force push, checks for new remote commits

### Branch Tracking
- 🌐 `git branch -vv` - List branches with tracking info
- 🌐 `git branch -u [remote]/[branch]` - Set upstream for branch
- 🌐 `git push --delete [remote] [branch]` - Delete remote branch
- 🔵 `git fetch --prune` - Remove remote-tracking branches that no longer exist

## 👥 Collaboration Workflows

## 🟣 GitHub CLI

### Installation
- 🔵 `brew install gh` - Install on macOS
- 🔵 `apt install gh` - Install on Ubuntu/Debian
- 🔵 `choco install gh` - Install on Windows

### Authentication
- 🌐 `gh auth login` - Authenticate with GitHub
- 🌐 `gh auth status` - Check authentication status
- 🌐 `gh auth logout` - Log out

### Repository Management
- 🌐 `gh repo create [name]` - Create a new repository
- 🌐 `gh repo clone [repository]` - Clone a repository
- 🌐 `gh repo fork [repository]` - Fork a repository
- 🌐 `gh repo view` - View repository in terminal
- 🌐 `gh repo view --web` - Open repository in browser

### Working with Issues
- 🌐 `gh issue list` - List issues
- 🌐 `gh issue status` - Show status of relevant issues
- 🌐 `gh issue view [issue-number]` - View an issue
- 🌐 `gh issue create` - Create a new issue (interactive)
- 🌐 `gh issue create --title "Bug" --body "Description"` - Create with specified title/body
- 🌐 `gh issue close [issue-number]` - Close an issue
- 🌐 `gh issue reopen [issue-number]` - Reopen an issue
- 🌐 `gh issue edit [issue-number]` - Edit an issue
- 🌐 `gh issue comment [issue-number]` - Add comment to an issue

### Pull Request Management
- 🌐 `gh pr list` - List pull requests
- 🌐 `gh pr status` - Show status of relevant PRs
- 🌐 `gh pr view [PR-number]` - View a pull request
- 🌐 `gh pr create` - Create a PR (interactive)
- 🌐 `gh pr create --title "Feature" --body "Description"` - Create with specified title/body
- 🌐 `gh pr checkout [PR-number]` - Check out a pull request locally
- 🌐 `gh pr merge [PR-number]` - Merge a pull request
- 🌐 `gh pr close [PR-number]` - Close a pull request
- 🌐 `gh pr ready [PR-number]` - Mark a draft PR as ready for review
- 🌐 `gh pr review [PR-number]` - Add a review to a PR
- 🌐 `gh pr comment [PR-number]` - Add comment to a PR
- 🌐 `gh pr diff [PR-number]` - View changes in a PR

### GitHub Actions
- 🌐 `gh workflow list` - List workflows
- 🌐 `gh workflow view [workflow-id]` - View a workflow
- 🌐 `gh workflow run [workflow-id]` - Manually trigger a workflow
- 🌐 `gh run list` - List recent workflow runs
- 🌐 `gh run view [run-id]` - View a workflow run
- 🌐 `gh run watch [run-id]` - Watch a run in progress
- 🌐 `gh run download [run-id]` - Download artifacts

### Releases
- 🌐 `gh release list` - List releases
- 🌐 `gh release view [tag]` - View a release
- 🌐 `gh release create [tag]` - Create a release (interactive)
- 🌐 `gh release create [tag] --notes "Release notes"` - Create with notes
- 🌐 `gh release create [tag] ./path/to/asset.zip` - Create with assets
- 🌐 `gh release delete [tag]` - Delete a release

### Gists
- 🌐 `gh gist create [file...]` - Create a gist
- 🌐 `gh gist list` - List your gists
- 🌐 `gh gist view [id]` - View a gist
- 🌐 `gh gist edit [id]` - Edit a gist
- 🌐 `gh gist clone [id]` - Clone a gist locally

### Other Features
- 🌐 `gh alias set [alias] [command]` - Create CLI alias
- 🌐 `gh api [endpoint]` - Make an authenticated GitHub API request
- 🌐 `gh secret list` - List repository secrets
- 🌐 `gh secret set [name]` - Set a repository secret

### Forks and Pull Requests (Git + GitHub CLI)
- 🌐 `gh repo fork [repository]` - Fork and clone repository
- 🔵 `git checkout -b feature-branch` - Create new branch
- 🔵 `git add .` - Stage changes
- 🔵 `git commit -m "Feature description"` - Commit changes
- 🌐 `git push -u origin feature-branch` - Push branch
- 🌐 `gh pr create` - Create PR (interactive)
- 🌐 `gh pr status` - Check PR status
- 🌐 `gh pr merge` - Merge when approved

### Code Review
- 🌐 `gh pr checkout [PR-number]` - Checkout PR locally
- 🌐 `gh pr diff [PR-number]` - View PR changes
- 🌐 `gh pr review [PR-number] --comment` - Add review comment
- 🌐 `gh pr review [PR-number] --approve` - Approve PR
- 🌐 `gh pr review [PR-number] --request-changes` - Request changes

## 🟣 GitHub Codespaces (Terminal-Based)

### Codespaces Management
- 🌐 `gh codespace list` - List your codespaces
- 🌐 `gh codespace create` - Create a codespace
- 🌐 `gh codespace delete [name]` - Delete a codespace
- 🌐 `gh codespace ssh [name]` - Connect to codespace via SSH
- 🌐 `gh codespace ports forward [local:remote]` - Forward ports
- 🌐 `gh codespace stop [name]` - Stop a codespace

## 🧰 Temporary Storage

### Stashing
- 🔵 `git stash` - Stash changes
- 🔵 `git stash save "message"` - Stash with description
- 🔵 `git stash list` - List stashes
- 🔵 `git stash show stash@{n}` - Show stash contents
- 🔵 `git stash apply stash@{n}` - Apply stash (keep in stash list)
- 🔵 `git stash pop` - Apply and remove most recent stash
- 🔵 `git stash drop stash@{n}` - Delete stash
- 🔵 `git stash clear` - Delete all stashes
- 🔵 `git stash push -m "message" [file]` - Stash specific file

## 🔍 Finding Information

### Searching
- 🔵 `git grep "pattern"` - Search for pattern in tracked files
- 🔵 `git grep -n "pattern"` - Search with line numbers
- 🔵 `git log -S "string"` - Search commits for changes to string
- 🔵 `git log --grep="pattern"` - Search commit messages
- 🔵 `git log --author="name"` - Filter commits by author
- 🔵 `git log --after="YYYY-MM-DD"` - Commits after date
- 🔵 `git log --before="YYYY-MM-DD"` - Commits before date

## 🔧 Advanced Git

### Submodules
- 🌐 `git submodule add [url] [path]` - Add submodule
- 🌐 `git submodule update --init --recursive` - Initialize and update all submodules
- 🌐 `git submodule update --remote` - Update submodules to latest remote version

### Tags
- 🔵 `git tag` - List all tags
- 🔵 `git tag [name]` - Create lightweight tag
- 🔵 `git tag -a [name] -m "message"` - Create annotated tag
- 🌐 `git push [remote] [tag]` - Push specific tag
- 🌐 `git push [remote] --tags` - Push all tags
- 🔵 `git tag -d [tag]` - Delete local tag
- 🌐 `git push [remote] :refs/tags/[tag]` - Delete remote tag

### Git Hooks
- 🔵 Edit hooks in `.git/hooks/` directory
- 🔵 Example pre-commit hook to run tests:
  ```bash
  #!/bin/sh
  npm test
  if [ $? -ne 0 ]; then
     echo "Tests failed, commit aborted"
     exit 1
  fi
  ```

### Advanced History Manipulation
- 🔵 `git filter-branch` - Rewrite history (use with caution)
- 🔵 `git bisect start` - Binary search for bug introduction
- 🔵 `git bisect bad` - Mark current commit as bad
- 🔵 `git bisect good [commit]` - Mark commit as good
- 🔵 `git bisect reset` - End bisect session

### Patches
- 🔵 `git format-patch [base-branch]` - Create patch files
- 🔵 `git apply [patch-file]` - Apply patch
- 🔵 `git am [patch-file]` - Apply patch and create commit

## 🚨 Troubleshooting

### Common Issues
- 🔵 `git reflog` - Show history of HEAD changes (useful for recovering lost commits)
- 🔵 `git fsck` - Check repository integrity
- 🔵 `git gc` - Clean up unnecessary files and optimize repository
- 🔵 `git prune` - Remove objects that are no longer pointed to
- 🔵 `git verify-pack -v .git/objects/pack/pack-*.idx | sort -k 3 -n | tail` - Find largest objects

### Conflict Resolution
- 🔵 After merge conflict appears:
  1. Edit files to resolve conflicts (look for conflict markers)
  2. `git add [resolved-file]`
  3. Continue with `git merge --continue` or `git rebase --continue`
- 🔵 `git mergetool` - Open visual merge tool

## 🚀 Workflow Examples

### Feature Branch Workflow with Git (offline then online)
```bash
# Start a new feature
git checkout -b feature-x main          # 🔵
# Make changes and commit
git add .                               # 🔵
git commit -m "Add feature X"           # 🔵
# Push to remote and create PR
git push -u origin feature-x            # 🌐
# Create PR on GitHub website           # 🌐
# After PR is approved, merge
git checkout main                       # 🔵
git pull                                # 🌐
git branch -d feature-x                 # 🔵
```

### Feature Branch Workflow with GitHub CLI
```bash
# Start a new feature
git checkout -b feature-x main          # 🔵
# Make changes and commit
git add .                               # 🔵
git commit -m "Add feature X"           # 🔵
# Push to remote and create PR in one go
git push -u origin feature-x            # 🌐
gh pr create --title "Add feature X" --body "Description"  # 🟣
# Check PR status
gh pr status                            # 🟣
# After PR is ready to merge
gh pr merge                             # 🟣
git checkout main                       # 🔵
git pull                                # 🌐
git branch -d feature-x                 # 🔵
```

### Sync Fork with Original Repo (Git)
```bash
# Add upstream if not done already
git remote add upstream https://github.com/original/repo.git  # 🌐
# Fetch and merge changes
git fetch upstream                      # 🌐
git checkout main                       # 🔵
git merge upstream/main                 # 🔵
git push origin main                    # 🌐
```

### Sync Fork with Original Repo (GitHub CLI)
```bash
# If fork already exists
gh repo sync owner/forked-repo         # 🟣
# Or to sync your current fork
gh repo sync                           # 🟣
```

### Cleanup Workflow
```bash
# Cleanup local branches
git fetch --prune                       # 🌐
git branch -vv | grep 'origin/.*: gone]' | awk '{print $1}' | xargs git branch -d  # 🔵
# Optimize repository
git gc                                  # 🔵
```

### Emergency Stash Workflow
```bash
# Need to switch branches with uncommitted work
git stash save "Emergency fix work in progress"  # 🔵
git checkout hotfix-branch              # 🔵
# Make and commit fix
git add .                               # 🔵
git commit -m "Fix critical bug"        # 🔵
git push origin hotfix-branch           # 🌐
# Go back to original work
git checkout original-branch            # 🔵
git stash pop                           # 🔵
```

## 📋 Git Configuration Templates

### Useful .gitconfig Aliases
```bash
[alias]
    s = status -sb
    c = commit
    ca = commit --amend
    co = checkout
    cb = checkout -b
    br = branch
    lg = log --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit
    unstage = restore --staged
    undo = reset HEAD~1 --mixed
    discard = restore
    last = log -1 HEAD
```

### Useful GitHub CLI Aliases
```bash
# Create these with: gh alias set <name> <command>

# View pull request in browser
gh alias set pv 'pr view --web'

# List pull requests assigned to you
gh alias set prm 'pr list --assignee @me'

# Create a pull request and automatically set yourself as assignee
gh alias set prc 'pr create --assignee @me'

# Checkout PR with an interactive selector
gh alias set pco 'pr checkout'

# Quick issue creation
gh alias set iss 'issue create --assignee @me'

# View repository insights
gh alias set stats 'repo view --json stargazerCount,forkCount,watchers,issues'

# List workflows in failure state
gh alias set broken 'workflow list --json name,state,conclusion -q ".[] | select(.conclusion == \"failure\") | .name"'
```

### Useful .gitignore Templates
```bash
# macOS
.DS_Store

# Node.js
node_modules/
npm-debug.log

# Python
__pycache__/
*.py[cod]
venv/
.env

# Java
*.class
target/

# IDE/Editors
.idea/
.vscode/
*.swp
*.swo
```
