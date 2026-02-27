# 我的博客

欢迎来到我的个性化博客！

## 快速开始

1. **创建仓库**：点击 [通过模板创建仓库](https://github.com/new?template_name=Gmeek-template&template_owner=Meekdai)，仓库名称建议为 `你的用户名.github.io`

2. **启用 Pages**：在仓库 Settings → Pages → Build and deployment → Source 下选择 `Github Actions`

3. **配置博客**：编辑 `config.json` 文件，配置你的博客信息

4. **访问博客**：打开 `https://你的用户名.github.io` 即可访问

---

## 配置文件说明

编辑根目录的 `config.json` 文件：

```json
{
    "title": "我的博客",
    "subTitle": "欢迎来到我的博客",
    "avatarUrl": "https://github.githubassets.com/favicons/favicon.svg",
    "email": "your-email@example.com",
    
    "background": {
        "desktop": "电脑端背景图片URL",
        "mobile": "手机端背景图片URL"
    },
    
    "admin": {
        "password": "123456"
    },
    
    "githubRepo": "your-username/your-repo",
    "guestbookLabel": "guestbook"
}
```

### 配置项详解

| 配置项 | 说明 | 示例 |
|--------|------|------|
| `title` | 博客标题 | "我的博客" |
| `subTitle` | 博客副标题 | "欢迎来到我的博客" |
| `avatarUrl` | 头像图片URL | "https://..." |
| `email` | 邮箱地址 | "example@mail.com" |
| `background.desktop` | 电脑端背景图 | 见下文 |
| `background.mobile` | 手机端背景图 | 见下文 |
| `admin.password` | 后台管理密码 | "123456" |
| `githubRepo` | GitHub仓库 | "username/repo" |
| `guestbookLabel` | 留言标签 | "guestbook" |

---

## 背景图片设置

### 方式一：使用 Unsplash 免费图片

Unsplash 提供大量免费高质量图片：

```json
"background": {
    "desktop": "https://images.unsplash.com/photo-1579546929518-9e396f3cc809?w=1920&q=80",
    "mobile": "https://images.unsplash.com/photo-1579546929518-9e396f3cc809?w=720&q=80"
}
```

推荐的一些背景图：
- 渐变色：`https://images.unsplash.com/photo-1579546929518-9e396f3cc809?w=1920&q=80`
- 星空：`https://images.unsplash.com/photo-1419242902214-272b3f66ee7a?w=1920&q=80`
- 山水：`https://images.unsplash.com/photo-1506905925346-21bda4d32df4?w=1920&q=80`
- 城市：`https://images.unsplash.com/photo-1477959858617-67f85cf4f1df?w=1920&q=80`

### 方式二：使用自己的图片

将图片上传到仓库的 `images/` 目录，然后配置路径：

```json
"background": {
    "desktop": "images/my-bg.jpg",
    "mobile": "images/my-bg-mobile.jpg"
}
```

### 方式三：使用渐变色

```json
"background": {
    "desktop": "linear-gradient(135deg, #667eea 0%, #764ba2 100%)",
    "mobile": "linear-gradient(135deg, #667eea 0%, #764ba2 100%)"
}
```

---

## 留言板功能

### 原理说明

留言板使用 GitHub Issues 存储留言：
1. 用户提交留言 → 自动跳转到 GitHub 创建 Issue
2. 博客读取 Issues → 显示留言列表
3. 站长回复 → 在 Issue 中添加回复内容

### 配置步骤

1. **配置仓库**：
   在 `config.json` 中设置 `githubRepo` 为你的仓库名：
   ```json
   "githubRepo": "your-username/your-username.github.io"
   ```

2. **创建标签**：
   在你的 GitHub 仓库中创建 `guestbook` 标签：
   - 进入仓库 → Issues → Labels → New label
   - 名称：`guestbook`
   - 颜色：任意

3. **用户留言**：
   - 访问博客，点击「留言板」选项卡
   - 填写昵称和留言内容
   - 点击「提交留言」
   - 会跳转到 GitHub，需要登录 GitHub 确认发布

4. **查看留言**：
   - 访问 `https://你的用户名.github.io/admin.html`
   - 输入密码登录（默认：123456）
   - 即可查看和管理所有留言

---

## 后台管理

### 访问地址
`https://你的用户名.github.io/admin.html`

### 登录密码
- 默认密码：`123456`
- **首次登录后请务必修改密码！**

### 功能说明

1. **留言管理**
   - 查看所有留言
   - 回复留言（会跳转到 GitHub 操作）
   - 查看原始 Issue

2. **密码设置**
   - 修改管理密码
   - 注意：由于是静态网页，密码保存在浏览器本地

---

## 页面说明

- **首页** (`index.html`)：博客主页，包含文章列表和导航
- **留言板** (`guestbook.html`)：独立留言页面
- **后台** (`admin.html`)：管理留言和修改密码

---

## 手动部署

当修改了 `config.json` 后，需要手动触发构建：

1. 进入仓库 → Actions
2. 点击 "Build Gmeek"
3. 点击 "Run workflow" → "Run workflow"

---

### Powered by [Gmeek](https://github.com/Meekdai/Gmeek)
