# Narrow React Prop Types

A GitHub Copilot skill for making React component prop types match the states reached by production code.

It uses live, non-test and non-Storybook call sites as the source of truth. Stories, tests, mocks, and demos must adapt to the stricter production contract instead of widening it.

## What it covers

- Identifies props widened for stories, mocks, tests, or demos.
- Makes always-supplied values and callbacks required.
- Preserves optionality only for meaningful production states.
- Removes fallback logic for unsupported states.
- Updates support code to satisfy the narrowed contract.
- Reports the live call sites and validation that justify each change.

## Install

Copy this repository into your Copilot skills directory:

```bash
git clone https://github.com/tanmayairbase/narrow-react-prop-types.git \
  ~/.agents/skills/narrow-react-prop-types
```

Invoke it with:

```text
/narrow-react-prop-types
```

See [`SKILL.md`](SKILL.md) for the complete workflow. The `references/` directory includes an example GitHub Actions workflow, agent memory file, and CI response template.
