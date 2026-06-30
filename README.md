# 中文学习小游戏 - GitHub Pages 部署指南

## 📦 部署文件说明

本目录已包含所有游戏的生产构建文件，可以直接部署到 GitHub Pages。

```
deploy/
├── index.html          # 游戏大厅入口页面
├── .nojekyll           # 禁用 Jekyll 处理
├── hsk-match/          # 汉字连连看
├── word-crush/         # 汉字消消乐
├── ztype-shooter/     # 拼音打字射击
└── flower-basket/      # 花篮接宝
```

## 🚀 部署步骤

### 第一步：安装 Git

如果尚未安装，访问 [https://git-scm.com](https://git-scm.com) 下载安装。

### 第二步：初始化 Git 仓库

在 **deploy** 文件夹中打开 Git Bash，执行以下命令：

```bash
# 进入 deploy 目录（根据你的实际路径）
cd "D:\个人项目\微信中文学习小游戏\中文小游戏\deploy"

# 初始化 Git 仓库
git init

# 添加所有文件
git add .

# 提交
git commit -m "Initial deploy: 4 Chinese learning games"
```

### 第三步：创建 GitHub 仓库

1. 打开 [github.com](https://github.com)，登录你的账号
2. 点击右上角 **+** → **New repository**
3. 仓库名称填写：`chinese-learning-games`
4. 选择 **Public**（公开才能用免费 Pages）
5. 不要勾选 "Add a README file"
6. 点击 **Create repository**

### 第四步：推送代码到 GitHub

复制 GitHub 页面上显示的命令，类似下面这样（替换为你的用户名）：

```bash
git remote add origin https://github.com/你的用户名/chinese-learning-games.git
git branch -M main
git push -u origin main
```

### 第五步：开启 GitHub Pages

1. 在 GitHub 仓库页面，点击 **Settings**（设置）
2. 左侧菜单点击 **Pages**
3. 在 "Build and deployment" 部分：
   - **Source** 选择 **Deploy from a branch**
   - **Branch** 选择 **main**，文件夹选择 **/(root)**
4. 点击 **Save**

### 第六步：访问你的游戏

等待 1-2 分钟后，你的游戏网址将会是：

```
https://你的用户名.github.io/chinese-learning-games/
```

例如：`https://zhangsan.github.io/chinese-learning-games/`

打开这个网址，就能看到游戏大厅，点击进入任意游戏！

---

## 🔄 后续更新（更新游戏时）

如果以后修改了游戏并重新构建：

```bash
# 重新构建游戏（在对应游戏目录中）
cd hsk-match && npm run build

# 复制新的 dist 文件到 deploy 目录
cp -r hsk-match/dist/* deploy/hsk-match/

# 进入 deploy 目录，提交更新
cd deploy
git add .
git commit -m "Update games: 修复 xxx"
git push origin main
```

更新后等待 1-2 分钟，GitHub Pages 会自动重新部署。

---

## 📋 游戏列表

| 游戏 | 路径 | 说明 |
|------|------|------|
| 汉字连连看 | `/hsk-match/` | 汉字与拼音/释义配对 |
| 汉字消消乐 | `/word-crush/` | 网格中寻找汉字配对 |
| 拼音打字射击 | `/ztype-shooter/` | 输入拼音击落敌人 |
| 花篮接宝 | `/flower-basket/` | 接住正确拼音的汉字 |

---

## ❓ 常见问题

**Q: 页面显示空白或 404？**  
A: 确认 GitHub Pages 设置中选择了 `main` 分支，等待 2-5 分钟后再刷新。

**Q: 游戏图片不显示？**  
A: 确保 `.nojekyll` 文件存在，已包含在部署文件中。

**Q: 可以用自己的域名吗？**  
A: 可以！在 GitHub Pages 设置中添加 Custom domain，并配置 DNS。

---

部署完成后，把网址分享给朋友，他们就可以在线玩游戏了！🎮
