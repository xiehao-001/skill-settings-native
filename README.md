# Skill Settings (Native)

`@chatecnu-work/dsh-skill-settings-native` · v0.1.0-dev · MulanPSL-2.0 AND MIT

Skill Settings owns the durable skill enable/disable preferences on the host side. The preferences are registered once, so they are available before any workspace or session opens and every agent reads the same record instead of keeping a copy per workspace.

The package supplies the `chatecnu-skills` settings namespace and the policy helper used by the companion skill availability gate.

## Highlights

- Registers one host-owned settings namespace, `chatecnu-skills`, instead of one preference record per workspace.
- Persists `disabled`, `enabled` and `defaultDisabled` skill lists, each defaulting to an empty array.
- Makes the policy readable before a workspace exists, so the settings screen works with no session open.
- Exports `SETTINGS_NAMESPACE` and a `./policy` entry so `@chatecnu-work/dsh-skill-control-native` resolves the same effective policy.
- Declares its Schemastery config from the same schema, marking the fields volatile.
- Pairs with the skill control plugin, which applies the stored lists before workspace policy.

## Install

Install this directory as a local DSH plugin bundle. From a shell:

```bash
dsh plugin --profile web add /absolute/path/to/skill-settings-native
```

Or add the directory through the **Plugins** panel in DSH (local bundle). Restart the DSH app after installation; plugins are activated from the bundle patch (`cordis.patch.yml`).

## Configuration

No configuration keys: the bundle patch inserts the plugin with defaults.

## Requirements

- DeepSeek Harness `>=0.2.1 <0.3.0`
- Peer packages: `@deepseek-ai/cordis`, `@deepseek-ai/dsh-settings`, `@deepseek-ai/schemastery`

## Notes and limits

- This package only stores preferences; enforcement happens in the companion skill control plugin.
- There is one host-level record, not a separate preference set per project or workspace.
- Version `0.1.0-dev` is a development-stage release.

## 中文文档

[README.zh-CN.md](./README.zh-CN.md)

## License

MulanPSL-2.0 AND MIT — see [LICENSE](./LICENSE) and, where present, [LICENSE-MIT](./LICENSE-MIT). Extracted from the ECNU EduWork distribution (https://github.com/ECNU/EduWork); upstream copyright and license notices are preserved.
