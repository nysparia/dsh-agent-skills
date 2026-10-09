---
name: dsh-third-party-plugin-install
description: 安装第三方 DSH/Cordis 插件时必须使用。
---

# 第三方 DSH 插件安装

## 适用范围

仅用于安装已经发布的第三方 DSH/Cordis 插件。用户未明确要求安装插件时不要触发。编写、审查、启用内置插件或开发 bundle 时使用其他适用的 skill。

## 工作流

1. 确认 npm 包名和可选版本号。没有明确包名时先搜索或询问，不要猜测。
2. 用户未明确授权执行安装时，只展示命令，不执行安装。
3. 安装时只使用：

   ```powershell
   dsh plugin --profile desktop add <npm包名或安装规格>
   ```

4. 指定版本时保留版本号：

   ```powershell
   dsh plugin --profile desktop add <包名>@<版本>
   ```

5. 安装完成后报告命令结果，并提示按需重启相关 DSH 进程以加载插件。
6. 不把 npm 下载成功直接视为插件运行成功；必要时检查 DSH 是否能正常启动以及插件功能是否可用。

## 禁止替代路径

不要使用以下方式安装第三方 DSH 插件：

- `plugin_manager install_bundle`
- 在 DSH profile 中运行 `npm install` 或 `pnpm add`
- 手动编辑 `~/.dsh/profiles/desktop/package.json`
- 手动编辑 `~/.dsh/profiles/desktop/cordis.patch.yml`
- 将 npm 包复制到 DSH profile 目录

## 完成证据

报告以下信息：

- 实际执行的 `dsh plugin` 命令
- 命令返回结果或失败原因
- 是否需要重启 DSH
- 已验证的加载或功能状态
