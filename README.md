# MacGyver

> "Breaking change? I've worked with worse."

**MacGyver** (or just **Mac**) is an intelligent agent that handles Dependabot alerts and GitHub CodeQL code scanning alerts the right way—not just bumping versions or flagging issues, but actually verifying changes work and fixing what breaks.

## What MacGyver Does

### Dependabot Alerts

Unlike standard Dependabot which simply proposes version bumps, MacGyver:

1. **Picks up Dependabot alerts and PRs**
2. **Runs the full test suite** to verify compatibility
3. **Builds the application** to catch compile-time issues
4. **Fixes breaking changes** when upgrades cause failures
5. **Updates the PR** with working code, not just version numbers

### CodeQL Code Scanning Alerts

MacGyver also monitors GitHub's CodeQL code scanning alerts and takes action:

1. **Triages CodeQL alerts** to understand severity and impact
2. **Analyzes the flagged code** to determine the root cause
3. **Implements fixes** that address the underlying issue, not just silence the alert
4. **Verifies the fix** by running tests and ensuring the alert is resolved
5. **Opens a PR** with a clear explanation of what was found and how it was fixed

CodeQL catches issues like:
- Potential security vulnerabilities
- Code quality problems
- Bug-prone patterns
- Performance anti-patterns

## The Name & Personality

### Why "MacGyver"?

The name comes from the classic TV series [MacGyver](https://en.wikipedia.org/wiki/MacGyver) (1985-1992), featuring a secret agent who could solve any problem with resourcefulness, scientific knowledge, and whatever materials were at hand—famously using duct tape and paperclips to escape impossible situations.

This perfectly captures what this agent does: when a major version bump breaks three unrelated things, Mac doesn't just revert or give up. He finds creative solutions with whatever's available in the codebase.

### Personality Traits

- **Resourceful**: Thinks laterally about solutions. If the obvious fix doesn't work, there's always another way.
- **Calm under pressure**: A failing CI pipeline is just another puzzle to solve.
- **Methodical**: Works through problems step by step, explaining the reasoning.
- **Optimistic but realistic**: Believes every problem has a solution, but won't pretend a breaking change is trivial.
- **Hands-on**: Doesn't just report problems—fixes them.

### Signature Phrases

- "Breaking change? I've worked with worse."
- "All I need is the changelog and five minutes."
- "Let's see what we're working with here..."
- "There's always a way. We just have to find it."

## Philosophy

The standard approach to security alerts is passive: Dependabot opens a PR that fails CI, CodeQL flags an issue in a dashboard, and both sit there until a human investigates. This creates alert fatigue and security debt.

MacGyver takes an active approach. Like the TV character who never waited for backup, this agent takes ownership of the problem end-to-end. It's not enough to identify that an upgrade is available or that code has a potential issue—the job isn't done until the fix is safely merged.

## Relationship with Elliot

MacGyver handles **automated security tooling alerts**—Dependabot for dependency vulnerabilities and CodeQL for code scanning issues flagged by GitHub's analysis.

[Elliot](https://github.com/phystack/agent-elliot) performs **deep, original analysis** of your codebase—finding vulnerabilities that automated tools miss by thinking like an attacker.

Together, they ensure both automated alerts get actioned *and* your code gets the thorough security review it deserves.

## License

MIT
