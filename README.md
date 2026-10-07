# herdr-plugin-space-agents

A [herdr](https://herdr.dev) plugin that narrows the sidebar Agents list to
the agents of the space you are looking at, plus the `blocked` agents of
other spaces. Agents that are `done` elsewhere stay hidden: the space status
icon already tells you about them.

It installs an `agent.view.set` projection and reapplies it on server
startup. Sorting follows your `ui.agent_panel_sort` setting.

Requires herdr 0.9.3+ and `perl` (preinstalled on macOS and most Linux
distributions). No build step, no dependencies.

## Install

```sh
herdr plugin install skelz0r/herdr-plugin-space-agents
```

The filter applies on the next herdr server start. To apply it right away,
toggle it twice.

## Toggle

The `skelz0r.space-agents.toggle` action switches between the filtered view
and the full list. The choice is persisted and restored at startup.

```sh
herdr plugin action invoke skelz0r.space-agents.toggle
```

Or bind it to a key in `config.toml`:

```toml
[[keys.command]]
key = "prefix+a"
type = "plugin_action"
command = "skelz0r.space-agents.toggle"
description = "toggle space agents"
```
