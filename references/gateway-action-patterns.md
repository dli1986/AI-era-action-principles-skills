# Gateway Action Patterns Reference

Use this file when a task needs help choosing a meaningful minimal action.

## Principle

A gateway action is the smallest practical action that exposes the real workflow.

It should be small, but it must not be trivial.

A gateway action should produce evidence and reveal at least one real constraint, failure mode, or design decision.

## Template

```markdown
## Gateway Minimal Action

### Objective
What this action proves.

### Use These Resources
- Resource 1 → why it matters
- Resource 2 → why it matters

### Do This
1. Essential step
2. Essential step
3. Essential step

### Evidence of Success
- Observable result
- Log/output/URL/file/decision created

### Save This
- Checklist item
- Decision note
- Failure mode
```

## Examples

### Cloud Platform

Not:

```text
Print hello world in a cloud function.
```

Better:

```text
Secure the account, deploy a tiny real endpoint behind the platform's recommended gateway, call it, inspect logs, estimate cost, and clean up resources.
```

Evidence:

- endpoint URL
- successful HTTP response
- log entry
- cost estimate
- cleanup checklist

### Machine Learning

Not:

```text
Import a library and print the version.
```

Better:

```text
Load a small real dataset, train a baseline, evaluate with the correct metric, change one feature or hyperparameter, and record the effect.
```

Evidence:

- baseline metric
- changed metric
- dataset schema note
- failure or leakage warning

### Model Platform

Not:

```text
Run a random tutorial snippet.
```

Better:

```text
Open the model's primary files, inspect configuration and tokenizer/processor assumptions, run the official inference path, and record model-specific quirks.
```

Evidence:

- config notes
- successful inference output
- tokenizer/processor notes
- compatibility constraints

### Frontend

Not:

```text
Create an empty app.
```

Better:

```text
Build one form that calls a real API, handles loading and error states, and persists or displays one result.
```

Evidence:

- working UI path
- API response
- error handling screenshot or note
- state-management decision

### Database

Not:

```text
Create a table.
```

Better:

```text
Model one real entity, insert sample data, query it with an index, inspect the query plan, and record tradeoffs.
```

Evidence:

- schema
- sample query
- query plan
- index decision

### New Platform

Not:

```text
Browse the homepage.
```

Better:

```text
Identify primary truth sources, run one official sample, change one meaningful parameter, observe the difference, and save a platform checklist.
```

Evidence:

- primary-source map
- successful official sample
- changed parameter result
- platform checklist
