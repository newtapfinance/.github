# Organization GitHub Standards

This repository contains organization-wide GitHub configuration and contribution standards.

These defaults are intended to provide a consistent development workflow across all repositories in the organization.

## Contents

```text
.github/
├── README.md
└── pull_request_template.md
```

## Jira + GitHub Workflow

All development work should be associated with a Jira ticket.

### Branch Naming

Branches must follow:

```text
<JIRA-TICKET>/<short-description>
```

Example:

```text
NTD-533/create-loan-changes
```

Additional examples:

```text
NTD-821/fix-duplicate-booking
NTD-1024/add-lms-validation
NTD-1132/update-kyc-flow
```

### Commit Messages

Commits should include the Jira ticket key:

```text
<JIRA-TICKET>: <description>
```

Example:

```text
NTD-533: implement loan creation
```

Other examples:

```text
NTD-821: fix duplicate booking validation
NTD-1024: add LMS facility validation
```

### Pull Requests

PR titles should include the Jira ticket key:

```text
NTD-533: Create loan changes
```

PR descriptions use the organization-wide PR template provided in:

```text
.github/pull_request_template.md
```

The organization-required Jira PR workflow applies this template when a PR is
created with an empty description. It also adds the linked Jira ticket to the
description and prefixes the PR title using the key from the source branch.
Branches must use `<JIRA-TICKET>/<short-description>`, for example
`NTD-123/feature-name`.

## Jira Linking

The Jira-GitHub integration automatically associates GitHub development activity with the corresponding Jira ticket when the Jira issue key is included in the branch name, commit message, or pull request.

For example:

```text
Jira:
NTD-533

        ↓

Branch:
NTD-533/create-loan-changes

        ↓

Commit:
NTD-533: implement loan creation

        ↓

Pull Request:
NTD-533: Create loan changes
```

This allows the Jira ticket to show the associated development activity such as branches, commits, and pull requests.

## Development Guidelines

Before creating a pull request, make sure:

* The branch follows the Jira naming convention.
* Commits contain the Jira ticket key.
* The PR title contains the Jira ticket key.
* The PR description is complete.
* Appropriate automated tests have been added or updated.
* Manual testing has been performed where applicable.
* Database changes include the required migration.
* API changes are documented in the PR.
* No debug code or unnecessary changes are included.
* CI checks are passing before requesting review.

## Repository-Specific Configuration

This repository provides **default organization-wide configuration**.

Individual repositories may have their own configuration where repository-specific requirements are necessary.

For example, a repository-specific PR template can override the organization default.

When adding repository-specific configuration, avoid unnecessarily diverging from the organization-wide standards.

## Goal

The goal of these standards is to maintain:

* Consistent GitHub workflows
* Automatic Jira ↔ GitHub linking
* Clear pull requests
* Better code reviews
* Traceable development history
* Consistent engineering practices across repositories

---

**Organization Engineering Standards**
