# Claude Code Permission Guardrails

[settings.json](./settings.json) is a strict, model-independent starting policy for Claude Code. It includes broad restrictions across development and system administration so you can remove rules you do not need. The restrictions below are **enabled in the file**.

Anthropic's [directory guide](https://code.claude.com/docs/en/claude-directory) and [settings.json entry](https://code.claude.com/docs/en/claude-directory#ce-settings-json) explain where this configuration belongs:

> files in `~/.claude` are personal configuration that applies across all your projects.

Sources checked on 2026-09-07.

## How This Policy Works

The policy has three layers:

1. **Explicit blocks:** sensitive paths, content-search and shell file-reading tools, common destructive commands, administrative tools, publication tools, and MCP tools with mutation-related names.
2. **Approval for other execution:** every Bash, PowerShell, MCP, WebFetch, and WebSearch call must pass an approval gate. This includes builds, tests, scripts, interpreters, unfamiliar tools, and shell commands normally treated as read-only.
3. **Additional isolation:** auto and bypass modes are disabled; the Bash sandbox is enabled where supported, with automatic approval and unsandboxed retries disabled.

The official [permission reference](https://code.claude.com/docs/en/permissions#manage-permissions) states:

> Rules are evaluated in order: deny, then ask, then allow.

A matching deny blocks the call. Other calls to the five gated tool families require approval, even if another settings file contains an allow. The built-in Grep tool is disabled; other built-in file tools keep their normal permission flow except for denied paths. The [mode settings](https://code.claude.com/docs/en/settings-reference#permissions) select the starting mode and disable automatic modes.

## Enabled Coverage

Command rules are paired for Bash and PowerShell. The file also includes native PowerShell cmdlets for Windows operations. Blank lines separate rule groups in the JSON.

| Area | Included restrictions |
| --- | --- |
| Secrets and credentials | Read and edit blocks for environment files, secret directories, private-key file types, package registry credentials, Terraform state and variable files, cloud credentials, SSH, Kubernetes, Docker, GitHub CLI, and Supabase temporary files. |
| Content searches and shell reads | The built-in Grep tool is disabled. Shell grep variants, ripgrep, cat/head/tail, sed/awk, pagers and selected binary readers are denied, including command-name prefixes, executable suffixes, and slash/backslash path forms. PowerShell Get-Content and Select-String are denied too. |
| Secret references in commands | Any Bash or PowerShell command containing `.env` or other listed credential filename fragments is denied, regardless of reader, argument order, or quoted path. |
| Policy and startup files | Edit blocks for `.claude`, MCP configuration, Claude instructions, Git configuration and hooks, CI workflows, and common shell profiles. |
| File deletion and overwrites | `rm`, `rmdir`, `unlink`, `shred`, `truncate`, `dd`, Windows deletion commands, `Remove-Item`, `Clear-Content`, and selected `find` deletion/execution forms. |
| Git history and configuration | Push, reset, clean, checkout, restore, rebase, stash, branch, tag, worktree, ref/config changes, credential helpers, and more; leading Git options and common hook-bypass forms are also blocked. |
| OS administration | Privilege elevation, ownership and ACL changes, disk formatting/partitioning, mounting, services, scheduled tasks, registry changes, shutdown, and process termination. |
| Cloud and infrastructure | Entire `aws`, `az`, `gcloud`, `terraform`, `tofu`, and `pulumi` command families. |
| Containers and clusters | Entire `docker`, `podman`, `kubectl`, and `helm` command families. |
| Databases and migrations | Entire `psql`, `mysql`, `mongosh`, `redis-cli`, `sqlite3`, `prisma`, and `supabase` command families. |
| Package publishing | npm publication, unpublication, deprecation, tags, ownership, access and tokens; Twine/uv publication; Cargo publication, yanking, and ownership. |
| Hosting and repository services | Entire GitHub CLI, Vercel, Netlify, Wrangler, and Fly command families, including documented `vc`, `ntl`, and `fly` aliases. |
| Network transfer and remote execution | Entire curl, wget, SSH/SCP/SFTP, rsync, and rclone families; PowerShell web requests and remote sessions. |
| MCP services | SQL execution and migrations, plus broad tool-name patterns for deletion, creation, updates, deployment, publishing, merging, messages, and uploads across server names. Every remaining MCP call requires approval. |
| Shell environment | Direct environment-dump commands; 29 named credential variables are removed from sandboxed subprocesses, including common cloud, database, package-registry, and API tokens. |

Whole-tool blocks are intentional: they also block source-code searches, shell file reads, help, status, dry runs, local container work, and read-only database queries. Command-prefix and substring rules can also block unrelated names or harmless commands: `*.env*` matches `.env.example` and JavaScript `process.env`. File patterns block public `.pem` certificates and nonsecret Terraform variables too. MCP substring patterns can block reads such as a tool named `get_post`.

Blocking only commands that spell out `.env` is insufficient: `rg -uuu TOKEN .` can search hidden files without naming them. This strict preset therefore blocks scanners themselves, including the built-in Grep tool; it does not rely only on path propagation for searches. See [ripgrep filtering](https://github.com/BurntSushi/ripgrep/blob/master/GUIDE.md#automatic-filtering).

For command semantics beyond Claude's matcher, use the relevant primary references: [Git](https://git-scm.com/docs/git), [GNU file utilities](https://www.gnu.org/software/coreutils/manual/coreutils.html), [Windows commands](https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/windows-commands), [Terraform](https://developer.hashicorp.com/terraform/cli/commands), [Docker](https://docs.docker.com/reference/cli/docker/), [database clients](https://www.postgresql.org/docs/current/app-psql.html), and [GitHub CLI](https://cli.github.com/manual).

## Installation and Subtraction

The repository stores this policy in `agent-configs/claude-code-desktop/permission-guardrails/`. Merge [settings.json](./settings.json) into `<project>/.claude/settings.json` for a shared project policy, or `~/.claude/settings.json` for personal use across projects. Windows normally uses `%USERPROFILE%\.claude`; `CLAUDE_CONFIG_DIR` can change this. For private project settings use `.claude/settings.local.json` and ignore it in Git if you create it manually. See [settings files](https://code.claude.com/docs/en/settings#settings-files).

Preserve unrelated settings. Permission and sandbox arrays merge across scopes: an empty array here does not clear existing grants or exceptions elsewhere. Inspect effective settings before relying on the result. See [settings precedence](https://code.claude.com/docs/en/settings#settings-precedence).

To relax the policy:

- **Permit Docker with approval:** remove both `Bash(docker *)` and `PowerShell(docker *)` from `deny`; keep the broad shell entries in `ask`.
- **Permit another blocked operation:** remove or narrow every matching deny. Adding an allow cannot override it. For example, `git -C` also matches the separate `git -*` restriction.
- **Permit a protected file:** narrow its Read and Edit patterns. Use a different filename for safe templates if you want to keep broad secret patterns.
- **Restore content searches:** remove the relevant Grep/scanner denies only after choosing your search boundary. Keep the secret Read/Edit and command-fragment blocks; a restored shell reader remains subject to the broad approval gate. Read rules alone do not isolate arbitrary subprocesses.
- **Edit CI, hooks, or this installed policy:** change the relevant Edit restriction yourself; those files are intentionally protected from agent edits.
- **Reduce routine prompts:** removing a broad `ask` entry changes the fallback for an entire tool. A narrow allow alone does not exempt a command from that broad ask.

The `//` path prefix anchors at the filesystem root and `~/` at the home directory. These patterns intentionally cover more than the current project. Validate them on your target OS. Use `Edit(path)` for write restrictions; `Write(path)` is not the path-rule mechanism. See [path rules](https://code.claude.com/docs/en/permissions#read-and-edit).

## Alternate Routes and Remaining Limits

An absolute executable path, `.exe` or `.cmd` suffix, alias, wrapper, SDK, or generated script may miss a specific command deny. For example, `npx wrangler deploy` does not start with `wrangler`; it still reaches the Bash or PowerShell approval gate. Approval authorizes the actual command and its subprocesses, so inspect script contents before approving them. This policy does not parse arbitrary program behavior. See [command matching](https://code.claude.com/docs/en/permissions#bash).

Read/Edit rules also feed the supported Bash sandbox, which restricts child processes. The configuration grants no network domains, Unix sockets, or local listeners itself and removes the listed credential variables from sandboxed commands. Other settings can add grants. See [sandbox configuration](https://code.claude.com/docs/en/sandboxing) and [credential protection](https://code.claude.com/docs/en/sandboxing#protect-credentials).

**Native Windows has no Claude Bash sandbox.** If the platform or required dependencies are unavailable, Claude can continue without it; the tool permission rules still apply. PowerShell and MCP tools are outside this Bash sandbox, and unlisted environment variables remain available. On a supported platform, add `"failIfUnavailable": true` under `sandbox` if startup must fail without isolation. Use [managed settings](https://code.claude.com/docs/en/managed-settings) and OS/container restrictions when users or other processes must not be able to weaken the policy.

A server name such as `supabase_dev_readonly` does not enforce read-only access. Configure the service itself with restricted credentials and scopes; for hosted Supabase, use its [read-only mode and project/feature restrictions](https://supabase.com/docs/guides/ai-tools/mcp#configuration-options). Tool-call permissions also do not sandbox separately configured hooks.

## Validation

The file passes its linked JSON schema and static checks for paired Bash/PowerShell rules, paired secret Read/Edit rules, mandatory approval gates, and the intended sandbox settings. These checks do not execute commands or prove Claude's runtime matching.

In the target Claude Code installation, run `claude doctor`, inspect `/status`, `/permissions`, and `/mcp`, and check `/sandbox` on a supported OS. See [configuration debugging](https://code.claude.com/docs/en/debug-your-config). Use a disposable project with dummy secrets and no shared remote or production credentials for behavioral checks:

| Case | Intended result |
| --- | --- |
| Direct `git reset HEAD --hard`, `git -C demo push`, `terraform -chdir=demo apply` | Denied by the reset, Git-option, and whole-Terraform rules respectively. |
| Direct `Remove-Item`, `psql`, `docker`, `npm publish`, or a matching MCP mutation tool | Denied. |
| `grep TOKEN .env`, `rg -uuu TOKEN .`, `/usr/bin/grep -R TOKEN .`, `rg.exe -uuu TOKEN .`, or PowerShell `Select-String`/`Get-Content` | Denied, including recursive searches that do not name the secret file. |
| A built-in Grep call, or a shell script command containing a literal `.env` reference | Denied. |
| A generated script, interpreter, absolute executable path, or unrecognized MCP tool | Approval required if no deny matches. |
| Root/nested environment files and protected CI/settings edits | Denied on matching paths. |
| `git status`, ordinary builds, and tests through a shell | Approval required. |

Runtime behavior has not been exercised in this workspace because the Claude CLI is unavailable.
