# AGENTS

## Purpose
Meta repo.
Hold many `chechiachang` playground/workshop repos as git submodules.
Single entrypoint for discovery + bulk update.

## Scope
- Keep only submodule pointers + `.gitmodules`.
- No feature code here.
- No cross-repo edits here.

## Submodule Policy
- Include repos with name matching: `*playground*` or `*workshop*`.
- Exclude self repo: `playgrounds`.
- Prefer SSH URL: `git@github.com:chechiachang/<repo>.git` (avoid HTTPS auth prompts).
- Path = repo name.

## Add Flow
1. List candidates:
   - `gh repo list chechiachang --limit 200 --json name,url`
2. Filter by name rule.
3. Add each:
   - `git submodule add git@github.com:chechiachang/<repo>.git <repo>`
4. Verify:
   - `git submodule status`
   - `git config -f .gitmodules --get-regexp '^submodule\..*\.path$'`

## Fix Broken Mapping
Symptom:
- `fatal: no submodule mapping found in .gitmodules for path '<x>'`

Fix:
1. `git rm --cached "<x>"`
2. `rm -rf "<x>" ".git/modules/<x>"`
3. Remove stale section in `.gitmodules`
4. `git add -A && git submodule sync --recursive`
5. Re-add submodule if needed.

## Update Flow
- Pull all submodules:
  - `git submodule update --init --recursive --remote`
- Order by latest commit time (desc):
  - `git submodule foreach --quiet 'printf "%s\t%s\t%s\n" "$(git log -1 --format=%ct)" "$(git log -1 --format=%ci)" "$name"' | sort -rn`
- Review pointer changes:
  - `git status`
  - `git diff --submodule`

## Commit Convention
- Commit only pointer/meta changes.
- Message style:
  - `chore(submodules): add <repo list>`
  - `fix(submodules): repair <repo> mapping`
  - `chore(submodules): bump refs`

## Guardrails
- Never add secrets.
- Never force-push.
- Never use interactive git flags.
- Keep repo clean: no stray non-submodule dirs for managed repos.
