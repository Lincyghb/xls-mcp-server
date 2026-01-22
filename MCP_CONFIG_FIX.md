# MCP 配置修复指南

## 问题
`xls-mcp-servers` 显示错误，因为安装的包中缺少 `cli_main` 函数。

## 解决方案

### 方案 1：使用 Python 直接运行（推荐）

修改 Cursor 的 MCP 配置文件，将配置改为：

```json
{
  "mcpServers": {
    "xls-mcp-servers": {
      "command": "python",
      "args": [
        "C:/Users/Administrator/AppData/Local/Programs/Python/Python312/Lib/site-packages/server.py"
      ]
    }
  }
}
```

**注意**：请将路径替换为你实际的 Python 安装路径。

### 方案 2：使用本地源代码（如果存在）

如果你本地有源代码目录，可以使用：

```json
{
  "mcpServers": {
    "xls-mcp-servers": {
      "command": "python",
      "args": [
        "F:/002/xls-mcp-servers/server.py"
      ],
      "cwd": "F:/002/xls-mcp-servers"
    }
  }
}
```

### 方案 3：重新安装包（需要修复源代码后重新发布）

如果源代码中有 `cli_main` 函数但安装的包中没有，需要：
1. 确保源代码中的 `server.py` 包含 `cli_main` 函数
2. 重新构建和发布包到 PyPI
3. 重新安装：`pip install --upgrade --force-reinstall xls-mcp-servers`

## 验证

配置修改后：
1. 重启 Cursor
2. 检查 MCP 服务器状态，应该显示为正常（绿色）
3. 尝试使用工具，如："读取 demo/NPC/cfg_npclist_demo.xls 文件"
