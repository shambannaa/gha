# GitHub Actions learning lab

A hands-on repo for learning GitHub Actions from the basics to exam level. Each lesson is one workflow file in `.github/workflows/`, named after the lesson number. Most files run from the **Actions** tab with the **Run workflow** button (`workflow_dispatch`), and a few also run on push.

The first lessons use shell commands (`echo`, `cat`, `cp`, `find`) as tools to see how steps, jobs and data behave on a runner. Later lessons add outputs, contexts, artifacts, matrices, reusable workflows, security and multi-environment deployments.

Reusable workflows used in the cross-repo lesson live in the companion repo [shambannaa/github-actions](https://github.com/shambannaa/github-actions).

## Lessons

| # | Lesson | What it teaches | File |
|---|---|---|---|
| 1 | Workflow anatomy | on, jobs, runs-on, steps, run, uses, actions/checkout, GITHUB_WORKSPACE, working-directory. Shows that a runner starts empty until checkout. | [1.yaml](.github/workflows/lab.yaml) |
| 2 | Creating and reading files | mkdir, touch, echo, printf, cat and heredocs inside a step. Files written in one step are visible to the next. | [2.yaml](.github/workflows/2.yaml) |
| 3 | Copy, move, delete, find | cp, mv, rm -f and find in a mini pipeline. What survives between steps and what does not. | [3.yaml](.github/workflows/3.yaml) |
| 4 | env and GITHUB_ENV | env at workflow, job and step level. Runtime variables through GITHUB_ENV. A checkout, verify and build pipeline. | [4.yaml](.github/workflows/4.yaml) |
| 5 | GITHUB_OUTPUT and step outputs | Step ids, outputs, and the difference between a shell variable and a ${{ }} expression. | [5.yaml](.github/workflows/5.yaml) |
| 6 | Jobs, needs and job outputs | Parallel jobs, ordering with needs, job-level outputs. Proves that env vars and files do not cross jobs. | [6.yaml](.github/workflows/6.yaml) |
| 7 | Default variables and contexts | GITHUB_* variables vs the github and runner contexts, and dumping a context with toJSON. | [7.yaml](.github/workflows/7.yaml) |
| 8 | Expressions and functions | Operators, contains, format, hashFiles, and the and/or pattern that works like if/else. | [8.yaml](.github/workflows/8.yaml) |
| 9 | if conditions and status functions | success, failure, always, cancelled. Why a step is skipped after a failure and how to run it anyway. | [9.yaml](.github/workflows/9.yaml) |
| 10 | Workflow commands and debugging | notice, warning, error, group, add-mask, job summary and debug logging. | [10.yaml](.github/workflows/10.yaml) |
| 11 | Inputs and triggers | workflow_dispatch inputs, push filters (branches, paths, tags) and schedule. | [11.yaml](.github/workflows/11.yaml) |
| 12 | Artifacts | upload-artifact and download-artifact to move files between jobs. | [12.yaml](.github/workflows/12.yaml) |
| 13 | Caching | actions/cache with hashFiles keys and the cache-hit output. | [13.yaml](.github/workflows/13.yaml) |
| 14 | Matrix strategies | Multiple axes, exclude, include and fail-fast. | [14.yaml](.github/workflows/14.yaml) |
| 14b | Include-only matrix | One job per environment, each with its own folder and config file. | [14b.yaml](.github/workflows/14b.yaml) |
| 15 | Secrets and variables | secrets vs vars, masking, and where each can be used. | [15.yaml](.github/workflows/15.yaml) |
| 16 | Concurrency and timeouts | concurrency groups, cancel-in-progress, timeout-minutes and continue-on-error. | [16.yaml](.github/workflows/16.yaml) |
| 17 | Composite action | A reusable bundle of steps called with uses ./.github/actions/greet. | [17.yaml](.github/workflows/17.yaml) |
| 18 | Reusable workflow | workflow_call with inputs and outputs, called from another workflow in the same repo. | [18.yaml](.github/workflows/18.yaml) |
| 19a | Reusable workflow from another repo | Calling the greet workflow stored in the github-actions repo with owner/repo/path@ref. | [19a.yml](.github/workflows/19a.yml) |
| 19 | Action types and pinning | JavaScript, Docker and composite actions, and pinning actions to a full commit SHA. | [19.yaml](.github/workflows/19.yaml) |
| 20 | GITHUB_TOKEN permissions | Least-privilege permissions and creating an issue with the gh CLI. | [20.yml](.github/workflows/20.yml) |
| 21 | Script injection | A vulnerable run step next to a safe one that passes the value through env. | [21.yml](.github/workflows/21.yml) |
| 21b | Hardening against injection | permissions {} plus an input validation step. | [21b.yaml](.github/workflows/21b.yaml) |
| 22 | Dependabot for actions | Keeps pinned action versions current. This is a config file, not a workflow. | [dependabot.yml](.github/dependabot.yml) |
| 23 | OIDC tokens | Requesting an OIDC token with id-token write and reading its claims. | [23.yaml](.github/workflows/23.yaml) |
| 24 | Fork PRs | pull_request vs pull_request_target and what each one can access. | [24.yaml](.github/workflows/24.yaml) |
| 25 | Environments | Environment variables and required reviewers for dev and prod. | [25.yaml](.github/workflows/25.yaml) |
| 26 | Build once, deploy many | One artifact promoted through dev, staging and prod. | [26.yaml](.github/workflows/26.yaml) |
| 27 | Reusable deploy pipeline | A shared deploy workflow, concurrency per environment and rollback by re-run. | [27.yaml](.github/workflows/27.yaml) |
| 28 | Runners | Hosted runner details and label based routing. | [28.yaml](.github/workflows/28.yaml) |
