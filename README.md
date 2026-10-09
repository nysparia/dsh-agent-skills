# DSH Agent Skills

用于记录和维护个人创建的 DeepSeek Harness Agent skills。

## 目录约定

每个 skill 放在 `skills/<skill-name>/` 下，并以 `SKILL.md` 作为入口。需要时可在同一目录添加 `references/`、`scripts/` 或 `assets/`。

## 安装到 DSH

将需要启用的 skill 复制或链接到 DSH 可发现的用户级目录，例如：

```text
~/.dsh/skills/<skill-name>/SKILL.md
```

仓库是源文件的唯一维护位置；启用目录中的文件不作为编辑副本。

## 官方约定

- `name` 使用 kebab-case。
- `description` 同时说明触发条件和产出或行为。
- 正文包含工作流、边界和可观察的完成证据。
- 测试正向触发、相邻不触发和显式调用。
