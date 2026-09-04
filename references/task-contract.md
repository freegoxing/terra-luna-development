# Luna Work Package

Give every delegated task all fields below. Omit none; write `none` where a
field does not apply.

```text
ROUTE: Luna; bounded exploration | implementation | verification | confirmed-root-cause fix

OBJECTIVE:
<one observable outcome>

CONTEXT:
<only the relevant requirement, interface details, and evidence>

SCOPE:
<what is in scope>

ALLOWED FILES:
- path/to/file

FORBIDDEN:
- architecture, API, dependency, and unrelated-refactor changes
- <task-specific exclusions>

REQUIREMENTS:
1. <precise requirement>

DONE WHEN:
- <acceptance criterion>

VALIDATION:
- <command>

RETURN:
- files changed or inspected
- concise findings/diff summary
- commands and exit codes
- remaining issues
```

## Required return shapes

```text
Status: success | partial | blocked | escalation_required

Changed / Found:
- path: concise note

Commands:
- command
  exit: 0

Issues:
- none
```

For an escalation, do not speculate or make an out-of-scope change:

```text
Status: escalation_required
Reason: <direct observation>
Evidence: <concise error, file, or behavior>
Decision needed: <specific Terra decision>
```
