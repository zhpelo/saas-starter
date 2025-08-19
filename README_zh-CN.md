# SaaS 启动模板

一个使用 Next.js 14、TypeScript 和 Tailwind CSS 构建的现代、生产就绪的 SaaS 启动模板。

![SaaS 启动模板](https://img.shields.io/badge/Next.js-14-black)
![TypeScript](https://img.shields.io/badge/TypeScript-5.0-blue)
![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-3.3-38B2AC)

## ✨ 特性

### 🎨 **美丽的设计系统**
- 简洁、现代化 UI
- 完全响应式设计
- 暗/亮模式支持
- 可定制的颜色方案
- 美丽的动画和过渡

### 🔧 **必要的 SaaS 组件**
- **身份验证**: 登录、注册、密码重置
- **登陆页面**: 英雄、特征、定价、证言、FAQ
- **博客系统**: 基于 Markdown 的博客，带有前言
- **案例研究**: 展示你的成功故事
- **仪表盘**: 用户仪表盘和分析
- **支付集成**: Stripe 准备好的支付系统

### 🛠 **开发者体验**
- **TypeScript**: 完全的类型安全
- **Next.js 14**: 最新的应用路由器，支持静态站点生成
- **Tailwind CSS**: 实用优先的 CSS 框架
- **组件库**: 可重用的 UI 组件
- **ESLint & Prettier**: 代码格式化和linting
- **响应式设计**: 移动优先的方法

### 📦 内容管理
- **Markdown 博客**: 使用前言的简单内容创建
- **案例研究**: 展示客户工作和结果
- **SEO 优化**: 元标签、结构化数据
- **快速性能**: 优化速度和 SEO

## 🚀 快速开始

### 前提条件
- Node.js 18+ 
- npm 或 yarn

### 安装

1. **克隆仓库**
```bash
git clone https://github.com/your-username/saas-starter-template.git
cd saas-starter-template
```

2. **安装依赖项**
```bash
npm install
# 或
yarn install
```

3. **启动开发服务器**
```bash
npm run dev
# 或
yarn dev
```

4. **打开浏览器**
访问 [http://localhost:3000](http://localhost:3000) 查看你的应用。

## 📁 项目结构

```
saas-starter-template/
├── src/
│   ├── app/                 # Next.js 应用路由器
│   │   ├── about/          # 关于页面
│   │   ├── blog/           # 博客页面
│   │   ├── cases/          # 案例研究
│   │   ├── globals.css     # 全局样式
│   │   ├── layout.tsx      # 根布局
│   │   └── page.tsx        # 首页
│   ├── components/         # React 组件
│   │   ├── ui/            # 基本 UI 组件
│   │   ├── layout/        # 布局组件
│   │   └── sections/      # 页面部分
│   └── lib/               # 实用函数
├── content/               # Markdown 内容
│   ├── blog/             # 博客文章
│   └── cases/            # 案例研究
├── public/               # 静态资产
├── package.json
├── tailwind.config.js
├── tsconfig.json
└── next.config.js
```

## 🎨 定制

### 颜色和主题

模板使用 CSS 自定义属性进行主题化。你可以在 `src/app/globals.css` 中定制颜色：

```css
:root {
  --primary: 142 76% 36%;        /* 绿色主色 */
  --primary-foreground: 355 7% 97%;
  --secondary: 240 4.8% 95.9%;
  /* ... 更多变量 */
}
```

### 组件

所有组件都是使用 TypeScript 和 Tailwind CSS 构建的。它们位于 `src/components/`：

- `ui/` - 基本 UI 组件 (按钮、卡片、徽章等)
- `layout/` - 布局组件 (头部、尾部)
- `sections/` - 页面部分 (英雄、特征、定价等)

### AI 辅助
你可以在 Cursor 中通过对话修改代码。

以下是一些示例 Prompt：
- 修改主题色：把项目的主色调改成粉色
- 增加语种：给项目增加法语支持
- 修改页面：修改主页，去掉 xx 模块

### 内容管理

#### 博客文章
在 `content/blog/` 中创建新博客文章，带有前言：

```markdown
---
title: "你的博客文章标题"
date: "2024-01-15"
excerpt: "你的文章简短描述"
author: "你的名字"
tags: ["SaaS", "Next.js", "教程"]
readTime: "5 分钟读取"
---

# 你的博客文章内容

在这里用 Markdown 写你的内容...
```

#### 案例研究
在 `content/cases/` 中创建新案例

### Contentful集成

#### 快速设置
1. **将数据结构导入到你的Contentful空间**：
   ```bash
   # 安装Contentful CLI
   npm install -g contentful-cli
   
   # 登录到Contentful
   contentful login
   
   # 导入提供的数据模型
   contentful space import --config cms/contentful/contentful-models-config.json
   ```

2. **配置环境变量**：
   ```bash
   # 在你的.env文件中
   CONTENTFUL_SPACE_ID=your_space_id
   CONTENTFUL_ACCESS_TOKEN=your_access_token
   CONTENTFUL_ENVIRONMENT=master
   ```

3. **将内容导出到本地Markdown**：
   ```bash
   npm run contentful:export
   ```

**包含什么**：
- **数据模型**: 预配置的博客和案例内容类型
- **多语言支持**: 支持英语（`en-US`）和中文（`zh-CN`）
- **富文本内容**: RichText转换为Markdown
- **资产管理**: 自动图像下载和本地化
- **语言映射**: `en` → `en-US`, `zh` → `zh-CN`

**输出结构**：
```
content/
├── en/blog/*.md        # 英语博客文章
└── zh/blog/*.md        # 中文博客文章
public/images/contentful/  # 下载的图像
```

详细的设置和配置，请见 `cms/contentful/README.md`. 



### 国际化

我们的项目支持多语言，你可以在 `dictionaries/` 目录中找到所有的翻译文件。详细的国际化设置和配置，请见 `dictionaries/README.md`。

### 数据统计
项目内置支持Google Analytics数据统计。

1. 开通 [Google Analytics](https://developers.google.com/analytics?hl=zh-cn)，得到统计代码
2. 把统计代码设置到环境变量中
```
NEXT_PUBLIC_GA_ID=G-xxxxx
```


## 📱 包含的页面

- **首页** (`/`) - 完整的登陆页面，包含所有部分
- **关于** (`/about`) - 关于页面，包含团队和公司信息
- **博客** (`/blog`) - 博客列表和单个文章页面
- **案例研究** (`/cases`) - 案例研究和成功故事
- **定价** - 在首页中包含，带有锚点链接

## 🎯 SEO 特性

- 元标签优化
- OpenGraph 和 Twitter Card 支持
- 结构化数据，提高搜索结果
- 站点地图生成准备
- 快速加载时间
- 移动优先的响应式设计

### robot.txt 和 sitemap.xml
项目提供了自动生成robot.txt 和 sitemap.xml的脚本。
只需要在 package.json 中修改gen:seo命令的 SITE_URL 为您自己的站点地址，然后运行：
`npm run gen:seo`即可。

## 🚀 部署
[![使用 EdgeOne Pages 部署](https://cdnstatic.tencentcs.com/edgeone/pages/deploy.svg)](https://console.cloud.tencent.com/edgeone/pages/new?template=saas-starter)

## 🤝 贡献

1. 分叉仓库
2. 创建你的特征分支 (`git checkout -b feature/amazing-feature`)
3. 提交你的更改 (`git commit -m '添加一些惊人的特征'`)
4. 推送到分支 (`git push origin feature/amazing-feature`)
5. 打开一个拉取请求

## 📄 许可

本项目根据 MIT 许可证进行许可 - 请查看 [LICENSE](LICENSE) 文件了解详情。

## 🙏鸣谢

- 使用 [Next.js](https://nextjs.org/) 构建
- 使用 [Tailwind CSS](https://tailwindcss.com/) 样式
- 来自 [Lucide React](https://lucide.dev/) 的图标

## 📞 支持

如果你对模板有任何问题或需要帮助：

- 在 GitHub 创建一个问题
- 发送邮件到 support@saas-starter.com
- 加入我们的 Discord 社区

---

**祝你愉快的构建！ 🚀** 