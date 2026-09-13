# CLIProxyAPI Provider for DeepSeek Harness

[English](./README_EN.md) | 简体中文

为 DeepSeek Harness 添加一个基于 OpenAI Responses API 的 `CLIProxyAPI` 模型供应商。

插件会自动从 CLIProxyAPI 获取模型列表，无需手动添加或维护模型。

## 使用方式

安装插件：

```powershell
npx @deepseek-ai/dsh plugin --profile web add github:router-for-me/dsh-cliproxyapi-provider
```

启动或重启 DeepSeek Harness Web：

```powershell
npx @deepseek-ai/dsh web
```

打开 Harness 后：

1. 进入 **设置 → 插件 → CLIProxyAPI**。
2. 填写 CLIProxyAPI 的 **Base URL**，例如
   `http://127.0.0.1:8317/v1`。
3. 填写 **API 密钥**；无鉴权服务可以留空。
4. 保存配置，模型列表会自动获取并定期刷新。

卸载插件：

```powershell
npx @deepseek-ai/dsh plugin --profile web remove @router-for-me/dsh-cliproxyapi-provider
```

卸载后重启 DeepSeek Harness Web 即可。

## 兼容性

此版本面向 DeepSeek Harness `0.1.5-rc.2` 及其后续兼容版本。它使用当前的 `settings.plugin.tab` 插槽、`settingsScope` 设置读写服务和 `ctx.remote` RPC 接口；升级后请重新安装插件并重启 Web 进程，使 DSH 载入新的客户端插件包。
