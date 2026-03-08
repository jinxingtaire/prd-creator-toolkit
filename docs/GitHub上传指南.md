# GitHub 上传指南

这是你第一次创建 GitHub 项目，这个指南将手把手教你如何上传。

## 📋 准备工作

### 1. 注册 GitHub 账号

如果还没有账号：
1. 访问 https://github.com
2. 点击 "Sign up"
3. 填写邮箱、密码、用户名
4. 验证邮箱

### 2. 安装 Git

**macOS**:
```bash
# 检查是否已安装
git --version

# 如果没有，用 Homebrew 安装
brew install git
```

**Windows**:
1. 下载 https://git-scm.com/download/win
2. 安装（一路 Next）

### 3. 配置 Git

```bash
# 设置用户名（会显示在提交记录中）
git config --global user.name "你的名字"

# 设置邮箱（使用 GitHub 注册邮箱）
git config --global user.email "your.email@example.com"

# 验证配置
git config --list
```

## 🚀 上传步骤

### 第1步：在 GitHub 创建仓库

1. 登录 GitHub
2. 点击右上角 "+" → "New repository"
3. 填写信息：
   - **Repository name**: `prd-creator-toolkit`
   - **Description**: `一个革命性的产品需求文档创作工具包，将传统静态 PRD 升级为文字+交互式原型的沉浸式汇报体验`
   - **Public** (公开) 或 **Private** (私有)
   - ❌ 不要勾选 "Initialize this repository with a README"（我们已经有了）
4. 点击 "Create repository"

### 第2步：初始化本地仓库

```bash
# 进入项目目录
cd /Users/jinxing/.openclaw/workspace/prd-creator-toolkit

# 初始化 Git 仓库
git init

# 添加所有文件
git add .

# 查看状态
git status

# 创建第一个提交
git commit -m "Initial commit: PRD Creator Toolkit v1.0

- 完整的 PRD 创作 SOP
- 4个交互式 HTML 原型模板
- Claude Code Skill
- 脱敏示例文档
- MIT License"
```

### 第3步：连接远程仓库

```bash
# 添加远程仓库（替换 yourusername 为你的 GitHub 用户名）
git remote add origin https://github.com/yourusername/prd-creator-toolkit.git

# 验证远程仓库
git remote -v
```

### 第4步：推送到 GitHub

```bash
# 推送到 main 分支
git branch -M main
git push -u origin main
```

**如果遇到认证问题**：

GitHub 现在需要使用 Personal Access Token (PAT) 而不是密码。

#### 创建 PAT：
1. GitHub 右上角头像 → Settings
2. 左侧菜单最下方 → Developer settings
3. Personal access tokens → Tokens (classic)
4. Generate new token (classic)
5. 勾选 `repo` 权限
6. 生成并复制 token（只显示一次！）

#### 使用 PAT：
```bash
# 推送时会要求输入用户名和密码
# 用户名：你的 GitHub 用户名
# 密码：粘贴刚才复制的 PAT
git push -u origin main
```

### 第5步：验证上传成功

1. 刷新 GitHub 仓库页面
2. 应该能看到所有文件
3. README.md 会自动显示在首页

## 📝 后续更新

### 修改文件后更新

```bash
# 查看修改了哪些文件
git status

# 添加修改的文件
git add .

# 或者只添加特定文件
git add README.md

# 提交修改
git commit -m "Update: 改进了 README 说明"

# 推送到 GitHub
git push
```

### 常用 Git 命令

```bash
# 查看状态
git status

# 查看提交历史
git log

# 查看最近3次提交
git log -3

# 查看文件修改内容
git diff

# 撤销未提交的修改
git checkout -- filename

# 查看远程仓库
git remote -v
```

## 🎨 美化你的 GitHub 仓库

### 1. 添加 Topics

在仓库页面：
1. 点击右侧 "About" 旁边的齿轮图标
2. 添加 Topics（标签）：
   - `prd`
   - `product-management`
   - `markdown`
   - `html5`
   - `prototyping`
   - `claude`
   - `documentation`

### 2. 添加 Banner 图片

创建一个好看的 Banner：
1. 使用 [Canva](https://www.canva.com) 或 Figma
2. 尺寸：1280×640px
3. 保存为 `docs/banner.png`
4. 在 README.md 顶部添加：

```markdown
![PRD Creator Banner](docs/banner.png)
```

### 3. 添加 Badges

在 README.md 顶部添加徽章：

```markdown
![License](https://img.shields.io/badge/license-MIT-green)
![Stars](https://img.shields.io/github/stars/yourusername/prd-creator-toolkit)
![Forks](https://img.shields.io/github/forks/yourusername/prd-creator-toolkit)
```

### 4. 添加 GIF 演示

录制原型演示 GIF：
1. 使用 [LICEcap](https://www.cockos.com/licecap/) (免费)
2. 或 [Kap](https://getkap.co/) (macOS)
3. 保存到 `docs/screenshots/`
4. 在 README 中引用

## 📢 推广你的项目

### 1. 社交媒体分享

- Twitter: 发推介绍项目
- LinkedIn: 分享到个人主页
- 微信: 分享到朋友圈/公众号

### 2. 提交到资源站

- [GitHub Trending](https://github.com/trending)
- [Product Hunt](https://www.producthunt.com/)
- [Hacker News](https://news.ycombinator.com/)

### 3. 写博客文章

写一篇文章介绍：
- 为什么创建这个工具？
- 如何使用？
- 有什么亮点？

## 🤝 接受贡献

### 1. 创建 CONTRIBUTING.md

```markdown
# 贡献指南

欢迎贡献！

## 如何贡献

1. Fork 项目
2. 创建分支 (`git checkout -b feature/AmazingFeature`)
3. 提交更改 (`git commit -m 'Add some AmazingFeature'`)
4. 推送到分支 (`git push origin feature/AmazingFeature`)
5. 创建 Pull Request

## 代码规范

- HTML: 使用 2 空格缩进
- CSS: 使用 BEM 命名规范
- Markdown: 遵循 CommonMark 规范
```

### 2. 创建 Issue 模板

在 `.github/ISSUE_TEMPLATE/` 创建模板文件。

### 3. 创建 Pull Request 模板

在 `.github/PULL_REQUEST_TEMPLATE.md` 创建模板。

## 📊 查看统计

### GitHub Insights

在仓库页面点击 "Insights" 查看：
- 访问量
- Star 增长
- Fork 数量
- 贡献者

### 添加 Star History

在 README 底部添加：

```markdown
[![Star History Chart](https://api.star-history.com/svg?repos=yourusername/prd-creator-toolkit&type=Date)](https://star-history.com/#yourusername/prd-creator-toolkit&Date)
```

## 🆘 常见问题

### Q: 推送时提示 "Permission denied"？

**A**: 检查：
1. 远程仓库 URL 是否正确？
2. 是否使用了 PAT 而不是密码？
3. PAT 是否有 `repo` 权限？

### Q: 如何删除已提交的敏感信息？

**A**: 使用 BFG Repo-Cleaner：
```bash
# 安装
brew install bfg

# 删除敏感文件
bfg --delete-files 敏感文件.txt

# 清理历史
git reflog expire --expire=now --all
git gc --prune=now --aggressive

# 强制推送
git push --force
```

### Q: 如何更改仓库名称？

**A**:
1. GitHub 仓库页面 → Settings
2. Repository name → 输入新名称
3. Rename
4. 本地更新远程 URL：
```bash
git remote set-url origin https://github.com/yourusername/new-name.git
```

## 📚 更多资源

- [GitHub 官方文档](https://docs.github.com/)
- [Git 教程](https://git-scm.com/book/zh/v2)
- [GitHub Skills](https://skills.github.com/)

---

**祝你的项目获得很多 Star！** ⭐️
