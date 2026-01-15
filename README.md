# README for 'Promote Helm Env' GitHub Action

## Description

<!-- AUTO-DOC-DESCRIPTION:START - Do not remove or modify this section -->

Promote app versions from a source environment to a target environment across all Helm apps, creating/refreshing PRs per app as needed.

<!-- AUTO-DOC-DESCRIPTION:END -->

The GitHub Action 'Promote Helm Env' automates the promotion of application versions between environments (e.g., from 'preproduction' to 'production'). It scans a set of Helm apps for version mismatches between a source and target environment's values file. If a mismatch is found, it creates or updates a Pull Request to promote the version.

## Features

- **Automated Promotion**: Detects version differences and synchronizes them.
- **Bulk Processing**: Can handle multiple apps matching a glob pattern.
- **Pull Request Management**: Automatically creates or updates PRs with relevant details.
- **Idempotency**: Checks for existing PRs and updates them if needed, avoiding duplicates.

## Inputs

<!-- AUTO-DOC-INPUT:START - Do not remove or modify this section -->

|                                          INPUT                                           |  TYPE  | REQUIRED |       DEFAULT       |                                         DESCRIPTION                                          |
|------------------------------------------------------------------------------------------|--------|----------|---------------------|----------------------------------------------------------------------------------------------|
|          <a name="input_source_env"></a>[source_env](#input_source_env)                  | string |   true   |                     |                Source environment <br>(e.g., preproduction, integration)                     |
|          <a name="input_target_env"></a>[target_env](#input_target_env)                  | string |   true   |                     |                Target environment <br>(e.g., production, preproduction)                      |
|          <a name="input_base_branch"></a>[base_branch](#input_base_branch)               | string |  false   |       `"main"`      |                            Base branch for promotion PRs                                     |
|             <a name="input_app_glob"></a>[app_glob](#input_app_glob)                     | string |  false   |   `"helm/apps/*"`   |                               Glob for apps to process                                       |

<!-- AUTO-DOC-INPUT:END -->
