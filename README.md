# SFDT Agent Skills

Ten agent skills that teach AI coding assistants how to work on **Salesforce DX**
projects — reviewing Apex and Flows, deploying safely, writing tests, running
static analysis, and driving the [`@sfdt/cli`](https://github.com/scoobydrew83/sfdt).

Works with Claude Code, Cursor, Codex, Windsurf, and any agent that reads the
[Agent Skills](https://code.claude.com/docs/en/skills) format.

## Install

```bash
# All ten skills
npx skills add scoobydrew83/sfdt-skills

# Just one
npx skills add scoobydrew83/sfdt-skills --skill sf-apex-review

# See what's in here first
npx skills add scoobydrew83/sfdt-skills --list
```

## The skills

| Skill | What it teaches |
|-------|-----------------|
| `sfdt-cli` | Using **and extending** the sfdt CLI — all commands, config system, `SFDT_` env vars, development guide |
| `sf-apex-review` | Production-grade Apex review: SOQL/DML in loops, CRUD/FLS, bulkification, batch idempotency, severity-tiered output with a deploy verdict |
| `sf-flow-review` | Flow metadata review: fault paths, bulk safety, hardcoded IDs, auto-layout, Flow-vs-Apex decisions |
| `sf-test` | Apex testing: running tests, coverage analysis, test-class standards, coverage-gap hunting, TestDataFactory pattern |
| `sf-deploy` | `sf project deploy` workflows: validate + quick deploy, destructive changes, test levels, troubleshooting |
| `sf-data` | SOQL best practices, bulk import/export, tree data seeding, governor limits |
| `sf-pmd-scan` | Salesforce Code Analyzer v5: scans, custom PMD rulesets, CI quality gates |
| `sf-org-audit` | Whole-project health audit with a structured remediation report |
| `sf-scratch-org` | Scratch org lifecycle: create, push/pull, conflicts, users, limits |
| `sf-lwc` | Lightning Web Components: wire adapters, events, SLDS, template rules, anti-patterns |

The nine `sf-*` skills work in **any** SFDX project — they don't require sfdt to
be installed or configured. They do know to prefer sfdt's native commands (smart
deploys, flow analysis, org audits) when a `.sfdt/` directory is present.

## Already using the sfdt CLI?

You don't need this repo. The skills ship inside `@sfdt/cli` — install them
straight into your project:

```bash
sfdt skills export --target claude   # .claude/skills/<name>/
sfdt skills export --target cursor   # .cursorrules
```

Full docs: <https://sfdt.dev/cli/skills>

## About this repo

This repo is **generated**. The skills are authored in the
[sfdt monorepo](https://github.com/scoobydrew83/sfdt) under `skills/` and synced
here on each release with:

```bash
sfdt skills export --target pack --out ../sfdt-skills
```

Open issues and PRs against [scoobydrew83/sfdt](https://github.com/scoobydrew83/sfdt),
not here — edits made directly to this repo are overwritten by the next sync.

Synced from `@sfdt/cli` v0.26.0.

## License

Apache-2.0. See [LICENSE](LICENSE).
