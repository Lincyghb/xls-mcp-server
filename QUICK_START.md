# 快速上传到 GitHub

## 🚀 一键执行命令

在项目目录 `f:\002\xls-mcp-servers` 下执行以下命令：

```powershell
# 1. 初始化 Git 仓库
git init

# 2. 添加所有文件
git add .

# 3. 创建初始提交
git commit -m "Initial commit: xls-mcp-servers v1.0.0"

# 4. 添加远程仓库（请确认你的 GitHub 用户名是 Lincyghb）
git remote add origin https://github.com/Lincyghb/xls-mcp-server.git

# 5. 推送到 GitHub
git branch -M main
git push -u origin main
```

## ⚠️ 重要提示

1. **确认 GitHub 用户名**: 如果你的 GitHub 用户名不是 `Lincyghb`，请先修改：
   - `pyproject.toml` 中的 URL
   - `README.md` 中的 URL
   - 或者使用你的实际用户名替换命令中的 `Lincyghb`

2. **创建 GitHub 仓库**: 在上传前，请先在 GitHub 上创建仓库：
   - 访问: https://github.com/new
   - 仓库名: `xls-mcp-server`
   - 不要初始化 README、.gitignore 或 LICENSE

3. **认证**: 如果推送时要求输入密码，请使用 GitHub Personal Access Token

## 📋 详细步骤

如需详细说明，请查看 `GITHUB_UPLOAD_GUIDE.md`
