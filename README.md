# codex-marketplace

Codex plugins by Digital Process Tools — the team behind DVSI.

```
codex plugin marketplace add Digital-Process-Tools/codex-marketplace
codex plugin add claude-jit-context@dpt-plugins
```

## Plugins

### claude-jit-context

Project knowledge that loads only when it is needed. Rules, conventions and domain notes are matched against the prompt, the file being touched, or the tool being run, and injected just in time instead of sitting in context all session.

Under Codex it binds SessionStart, UserPromptSubmit, PreToolUse and PostToolUse to the same `scripts/*.sh` Claude Code runs. A `mode: block` rule refuses a tool call, and the refusal is honoured.

<https://github.com/Digital-Process-Tools/claude-jit-context>

### remember

Continuous memory for your agent. Sessions are extracted, summarized, and compressed into layered daily logs. It remembers what you did yesterday.

<https://github.com/Digital-Process-Tools/claude-remember>

## Why this is a separate repo

Claude Code reads `.claude-plugin/marketplace.json`; Codex reads `.agents/plugins/marketplace.json`. The two schemas do not share a source shape, and the plugin lists are not the same list — three of the five plugins in [claude-marketplace](https://github.com/Digital-Process-Tools/claude-marketplace) ship no Codex manifest and are deliberately absent here.

Both catalogues are hand-maintained. A plugin added to one is not added to the other until someone does it.

## Trusting the hooks

Codex will not run a plugin's hooks until you trust them. Until you do, they are skipped in silence: no warning, no non-zero exit, no transcript line, the tool call simply proceeds. So if a rule seems not to fire, check trust before you check the rule.

## Licence

Each plugin carries its own. Both listed here are under the Community License, in their own repository.
