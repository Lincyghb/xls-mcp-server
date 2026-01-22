# GitHub 上传指南

本指南将帮助你将 `xls-mcp-servers` 项目上传到 GitHub。

## 📋 前置检查

### 1. 确认 GitHub 仓库地址

根据 `pyproject.toml` 配置，项目应该上传到：
- **仓库地址**: `https://github.com/Lincyghb/xls-mcp-server`
- **仓库名称**: `xls-mcp-server`（注意：不是 xls-mcp-servers）

⚠️ **重要**: 请确认你的 GitHub 用户名是 `Lincyghb`，如果不是，需要修改 `pyproject.toml` 中的 URL。

### 2. 检查需要排除的文件

已配置 `.gitignore`，会自动排除：
- `__pycache__/`、`*.pyc` 等 Python 缓存文件
- `test_output.xls` 测试输出文件
- `.vscode/`、`.idea/` 等 IDE 配置
- `dist/`、`build/` 等构建文件

## 🚀 上传步骤

### 步骤 1: 在 GitHub 上创建仓库

1. 登录 GitHub，访问：https://github.com/new
2. **Repository name**: 输入 `xls-mcp-server`
3. **Description**: 输入 `MCP Server for reading and writing .xls Excel files (Excel 97-2003 binary format)`
4. **Visibility**: 选择 Public（公开）或 Private（私有）
5. **不要**勾选以下选项（  因为本地已有代码）：
   - ❌ Add a README file
   - ❌ Add .gitignore
   - ❌ Choose a license
6. 点击 **Create repository**

### 步骤 2: 初始化本地 Git 仓库

在项目目录下执行以下命令：

```bash
# 进入项目目录
cd f:\002\xls-mcp-servers

# 初始化 Git 仓库
git init

# 添加所有文件到暂存区
git add .

# 创建初始提交
git commit -m "Initial commit: xls-mcp-servers v1.0.0"
```

### 步骤 3: 连接到 GitHub 仓库

```bash
# 添加远程仓库（请将 YOUR_USERNAME 替换为你的 GitHub 用户名）
git remote add origin https://github.com/Lincyghb/xls-mcp-server.git

# 或者使用 SSH（如果你配置了 SSH 密钥）
# git remote add origin git@github.com:Lincyghb/xls-mcp-server.git

# 验证远程仓库配置
git remote -v
```

### 步骤 4: 推送代码到 GitHub

```bash
# 推送代码到 main 分支
git branch -M main
git push -u origin main
```

如果 GitHub 仓库默认分支是 `master`，使用：
```bash
git branch -M master
git push -u origin master
```

## 🔧 后续操作

### 添加 LICENSE 文件（可选但推荐）

如果项目使用 MIT 许可证，创建 `LICENSE` 文件：

```bash
# 在项目根目录创建 LICENSE 文件
```

MIT License 模板内容：
```
MIT License

Copyright (c) 2024 Lincy

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

### 创建 Release Tag（推荐）

为 v1.0.0 版本创建标签：

```bash
# 创建标签
git tag -a v1.0.0 -m "Release version 1.0.0"

# 推送标签到 GitHub
git push origin v1.0.0
```

### 配置 GitHub Actions（可选）

项目已包含 `.github/workflows/` 目录，包含：
- `deploy.yml` - 部署工作流
- `docker-build.yml` - Docker 构建工作流

这些工作流会在推送代码后自动运行（如果配置正确）。

## 📝 检查清单

上传前请确认：

- [ ] ✅ `.gitignore` 已配置，排除了敏感文件
- [ ] ✅ `pyproject.toml` 中的 GitHub URL 正确
- [ ] ✅ `README.md` 中的 GitHub URL 正确
- [ ] ✅ 没有包含敏感信息（API keys、tokens 等）
- [ ] ✅ 测试文件 `test_output.xls` 已排除
- [ ] ✅ 所有代码文件已添加
- [ ] ✅ 提交信息清晰明确

## 🐛 常见问题

### 问题 1: 推送时要求输入用户名密码

**解决方案**: 使用 Personal Access Token (PAT)
1. GitHub → Settings → Developer settings → Personal access tokens → Tokens (classic)
2. 生成新 token，勾选 `repo` 权限
3. 推送时使用 token 作为密码

### 问题 2: 远程仓库已存在内容

**解决方案**: 先拉取再推送
```bash
git pull origin main --allow-unrelated-histories
git push -u origin main
```

### 问题 3: GitHub 用户名不匹配

**解决方案**: 修改 `pyproject.toml` 和 `README.md` 中的 URL
```bash
# 使用搜索替换
# 将 Lincyghb 替换为你的实际用户名
```

## 📚 参考资源

- [GitHub 创建仓库](https://docs.github.com/en/get-started/quickstart/create-a-repo)
- [Git 基础命令](https://git-scm.com/docs)
- [GitHub Actions 文档](https://docs.github.com/en/actions)

## ✅ 完成

上传完成后，你的项目将可以在以下地址访问：
- **仓库**: https://github.com/Lincyghb/xls-mcp-server
- **PyPI**: https://pypi.org/project/xls-mcp-servers/

祝上传顺利！🎉
