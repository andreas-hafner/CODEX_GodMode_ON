# Review Start Prompt

Use this for analysis, review, and architecture assessment.

These prompts assume the global install has already been applied.

## Prompt

```text
$godmode-workflow

GODMODE REVIEW

Goal: <system / change / problem to assess>

Inspect the current workspace first.
Loop: inspect -> analyze -> verify -> report.
Findings first. No code changes unless asked.
```

## Best for

- code or architecture reviews
- understanding an existing repo or subsystem
- risk, scope, or integration assessments before implementation

## Optional extras

- affected files or modules
- review focus such as `bugs`, `regressions`, `architecture`, or `release risk`
- whether you want analysis only or a later implementation proposal
- prepend `$web-platforms`, `$apple-platforms`, or `$flutter-dart` if stack-specific guidance should trigger immediately
- whether local workspace rules should override the global defaults
