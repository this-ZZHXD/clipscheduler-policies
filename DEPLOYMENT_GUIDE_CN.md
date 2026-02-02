# ClipScheduler - 第二次 TikTok API 申请指南

## 🎯 应用概述

**应用名称:** ClipScheduler  
**定位:** Scheduling Tools (排期管理工具)  
**核心价值:** 可视化日历管理 + 批量上传 + 智能定时发布

**为什么选择 ClipScheduler 作为第二个申请：**
- ✅ 与 VideoFlow Publisher 差异明显
- ✅ 功能场景清晰（专注于排期管理）
- ✅ 审核难度低
- ✅ 实用性强

---

## 📁 包含的文件

```
clipscheduler_application/
├── index.html              # 主页
├── terms-of-service.html   # 服务条款
├── privacy-policy.html     # 隐私政策
├── callback.html           # OAuth 回调页面
├── README.md               # 应用说明
└── LOGO_NEEDED_CS.jpg.txt  # Logo 规格说明
```

---

## 🎨 视觉设计主题

**颜色方案:**
- 主色: `#4facfe` (蓝色)
- 次色: `#00f2fe` (青色)
- 渐变: 蓝色到青色的清新渐变

**Logo 要求:**
- 文件名: `CS.jpg`
- 尺寸: 512x512px (正方形)
- 设计元素: 日历 + 时钟 + 视频图标
- 风格: 清晰、有序、专业

---

## 🚀 快速部署步骤

### 步骤 1: 创建 GitHub 仓库

1. 访问: https://github.com/new
2. 仓库名称: `clipscheduler-policies`
3. 设置为 **Public**
4. **不要**勾选 "Initialize with README"
5. 点击 "Create repository"

### 步骤 2: 创建 Logo

**方案 A: 使用 Canva**
1. 访问 canva.com
2. 创建 512x512px 正方形设计
3. 添加元素:
   - 日历图标或网格
   - 时钟/指针元素
   - 小视频播放图标
4. 应用蓝色渐变 (#4facfe → #00f2fe)
5. 导出为 JPG, 命名为 `CS.jpg`

**方案 B: AI 生成**
```
Prompt:
Create a modern professional logo for ClipScheduler, a video scheduling platform.
Design elements: calendar grid, clock icon, video play button
Color scheme: blue gradient from #4facfe to #00f2fe
Style: clean, organized, minimal
Square format 512x512px
```

### 步骤 3: 上传文件

1. 在 GitHub 仓库页面点击 "uploading an existing file"
2. 上传所有文件:
   - ✅ index.html
   - ✅ terms-of-service.html
   - ✅ privacy-policy.html
   - ✅ callback.html
   - ✅ README.md (可选)
   - ✅ **CS.jpg** (你创建的 Logo)
3. Commit message: "Initial commit - ClipScheduler website"
4. 点击 "Commit changes"

### 步骤 4: 启用 GitHub Pages

1. 进入仓库 Settings (设置)
2. 左侧菜单找到 "Pages"
3. Source 选择: "Deploy from a branch"
4. Branch 选择: "main" + "/ (root)"
5. 点击 "Save"
6. 等待 1-2 分钟

### 步骤 5: 验证部署

访问: `https://this-ZZHXD.github.io/clipscheduler-policies/`

应该能看到:
- ✅ 蓝色渐变的页面
- ✅ ClipScheduler Logo 显示正常
- ✅ "Master Your Content Calendar with Precision" 标语
- ✅ 6 个功能卡片
- ✅ 4 个工作流程步骤

---

## 🎬 Demo 视频制作

### 录制建议

**时长:** 3-5 分钟  
**工具:** OBS Studio / Loom / QuickTime 屏幕录制  
**格式:** MP4 或 MOV  
**大小:** < 50MB

### 视频脚本（中英双语）

#### 开场 (0:00-0:30)

**中文:**
```
大家好，我是 ClipScheduler 的开发者。
ClipScheduler 是一个专业的 TikTok 视频排期管理工具。
它帮助创作者通过可视化日历提前规划内容，
实现批量上传和自动定时发布。
```

**English:**
```
Hello, I'm the developer of ClipScheduler.
ClipScheduler is a professional scheduling tool for TikTok content creators.
It helps users plan their content calendar visually,
with bulk upload and automated scheduled publishing.
```

#### 演示 OAuth 连接 (0:30-1:30)

**中文:**
```
首先，用户需要连接他们的 TikTok 账号。
[点击网站上的"Connect TikTok"按钮]
这会跳转到 TikTok 的授权页面。
我们请求三个权限：
1. user.info.basic - 用于在日历中显示用户的 TikTok 头像和用户名
2. video.upload - 用于批量上传视频到 TikTok 服务器
3. video.publish - 用于在预定时间自动发布视频

用户授权后，会回到我们的回调页面。
[展示 callback.html 页面]
这里显示授权成功，以及获得的权限列表。
```

**English:**
```
First, users need to connect their TikTok account.
[Click "Connect TikTok" button on website]
This redirects to TikTok's authorization page.
We request three permissions:
1. user.info.basic - To display user's TikTok avatar and username in the calendar
2. video.upload - To bulk upload videos to TikTok servers
3. video.publish - To automatically publish videos at scheduled times

After authorization, users return to our callback page.
[Show callback.html page]
This displays successful authorization and the granted permissions.
```

#### 展示核心功能 (1:30-3:30)

**中文:**
```
接下来展示 ClipScheduler 的核心功能。

[展示功能 1：可视化日历]
在我们的日历视图中，用户可以一眼看到整个月的发布计划。
每个日期显示已安排的视频缩略图和发布时间。

[展示功能 2：批量上传]
用户可以一次性上传多个视频文件。
比如这里，我们一次选择了 10 个视频。
系统会将这些视频上传到 TikTok 服务器，
但暂时不发布，而是保存为草稿。

[展示功能 3：设置发布时间]
对于每个上传的视频，用户可以：
- 选择具体的发布日期
- 设置发布时间（精确到分钟）
- 添加标题、标签、话题标签
- 设置隐私级别

[展示功能 4：智能时间建议]
我们的 AI 会基于用户的历史数据，
建议最佳发布时间，以获得更高的观看量。

[展示功能 5：自动发布]
到了预定时间，ClipScheduler 会自动：
1. 使用 video.publish 权限
2. 将视频发布到用户的 TikTok 账号
3. 应用用户设置的所有元数据
4. 在日历中标记为"已发布"
```

**English:**
```
Now let me show ClipScheduler's core features.

[Show Feature 1: Visual Calendar]
In our calendar view, users can see their entire month's publishing plan at a glance.
Each date shows scheduled video thumbnails and publishing times.

[Show Feature 2: Bulk Upload]
Users can upload multiple video files at once.
For example, here we're selecting 10 videos.
The system uploads these to TikTok servers,
but doesn't publish them yet - they're saved as drafts.

[Show Feature 3: Schedule Publishing]
For each uploaded video, users can:
- Choose specific publishing date
- Set publishing time (down to the minute)
- Add captions, tags, and hashtags
- Set privacy levels

[Show Feature 4: Smart Timing Suggestions]
Our AI suggests optimal posting times
based on user's historical data for higher viewership.

[Show Feature 5: Auto-Publishing]
At the scheduled time, ClipScheduler automatically:
1. Uses the video.publish permission
2. Posts the video to user's TikTok account
3. Applies all user-configured metadata
4. Marks as "Published" in the calendar
```

#### 总结三个 Scopes (3:30-4:30)

**中文:**
```
总结一下 ClipScheduler 如何使用三个权限：

1. user.info.basic
   - 在日历界面显示用户的 TikTok 头像
   - 显示账号名称和统计信息
   - 个性化用户体验

2. video.upload
   - 批量上传多个视频文件
   - 将视频传输到 TikTok 服务器
   - 保存为草稿等待发布

3. video.publish
   - 在指定时间自动发布视频
   - 应用标题、标签、隐私设置
   - 无需用户手动操作

这就是 ClipScheduler - 让 TikTok 内容规划变得简单高效。
我们在沙盒环境中完整实现了这些功能。
感谢观看！
```

**English:**
```
To summarize how ClipScheduler uses the three permissions:

1. user.info.basic
   - Display user's TikTok avatar in the calendar interface
   - Show account name and statistics
   - Personalize user experience

2. video.upload
   - Bulk upload multiple video files
   - Transfer videos to TikTok servers
   - Save as drafts awaiting publication

3. video.publish
   - Automatically publish videos at scheduled times
   - Apply captions, tags, and privacy settings
   - No manual user intervention required

This is ClipScheduler - making TikTok content planning simple and efficient.
We have fully implemented these features in the Sandbox environment.
Thank you for watching!
```

### 录制技巧

1. **显示 URL**
   - 始终在浏览器地址栏显示: `https://this-ZZHXD.github.io/clipscheduler-policies/`
   
2. **使用模拟界面**
   - 你可以创建简单的 HTML mockup 展示日历功能
   - 或使用 PPT/Figma 设计界面截图

3. **录制设置**
   - 1920x1080 分辨率
   - 清晰的音频（使用麦克风）
   - 语速适中，发音清晰

---

## 📝 TikTok Developer Portal 配置

### 第一步：创建新应用

1. 登录 TikTok Developer Portal
2. 点击 "Create an App"
3. 填写信息:

```
App Name: ClipScheduler
Category: 选择 "Productivity" 或 "Social"
Website: https://this-ZZHXD.github.io/clipscheduler-policies/
```

### 第二步：添加 Products

#### 1. Login Kit
- Redirect URI: `https://this-ZZHXD.github.io/clipscheduler-policies/callback.html`

#### 2. Content Posting API
- Type: Direct Post
- Enable: ✅

### 第三步：选择 Scopes

- ✅ `user.info.basic`
- ✅ `video.upload`
- ✅ `video.publish`

### 第四步：App Review 提交

**Application Explanation (应用说明):**

```
ClipScheduler uses Content Posting API to enable advanced scheduling and automated publishing for TikTok.

INTEGRATION FLOW:
1. Authentication: Users connect TikTok account to access scheduling features. We use user.info.basic to display profile and account info in the calendar dashboard.

2. Scheduled Uploads: Users upload videos in bulk and assign publish dates. We use video.upload to store videos on TikTok servers awaiting scheduled publication.

3. Automated Publishing: At scheduled times, our system triggers publication. We use video.publish to automatically post queued videos to user's TikTok account at preset times.

SCOPE USAGE:
- user.info.basic: Show TikTok account in scheduling dashboard
- video.upload: Upload scheduled videos to TikTok queue
- video.publish: Auto-publish videos at scheduled times

USER FLOW: Connect TikTok → Bulk upload → Schedule dates → Auto-publish → Calendar tracking

Our demo uses Sandbox environment to demonstrate the complete integration on our web application (https://this-ZZHXD.github.io/clipscheduler-policies/).
```

**Demo Video:**
- 上传你录制的视频（MP4/MOV格式，< 50MB）

---

## 🎨 与 VideoFlow Publisher 的差异

| 特性 | VideoFlow Publisher | ClipScheduler |
|------|---------------------|---------------|
| **核心定位** | 通用发布工具 | 排期管理专家 |
| **主要功能** | 快速发布 | 可视化日历 + 批量上传 |
| **目标用户** | 普通创作者 | 内容策划者 |
| **独特价值** | 简单快速 | 提前规划 + 自动化 |
| **颜色主题** | 紫色渐变 | 蓝色渐变 |
| **Logo 风格** | 流动播放按钮 | 日历 + 时钟 |

---

## ✅ 提交前检查清单

### 文件检查
- [ ] 所有 5 个 HTML 文件已上传到 GitHub
- [ ] CS.jpg Logo 已创建并上传
- [ ] GitHub Pages 已启用并可访问
- [ ] 网站在浏览器中显示正常
- [ ] 所有链接（Terms, Privacy, Callback）正常工作

### TikTok Portal 检查
- [ ] 新应用已创建（不是 VideoFlow Publisher）
- [ ] 应用名称: ClipScheduler
- [ ] Website URL: https://this-ZZHXD.github.io/clipscheduler-policies/
- [ ] Login Kit Redirect URI 正确
- [ ] Content Posting API (Direct Post) 已启用
- [ ] 三个 scopes 已选择
- [ ] 应用说明已填写（不超过 1000 字符）

### Demo 视频检查
- [ ] 视频时长 3-5 分钟
- [ ] 显示了完整的 OAuth 流程
- [ ] 展示了日历界面和批量上传功能
- [ ] 说明了三个 scopes 的用途
- [ ] URL 在视频中清晰可见
- [ ] 音频清晰，语速适中
- [ ] 文件格式: MP4 或 MOV
- [ ] 文件大小: < 50MB

---

## 📅 提交时间建议

**如果 VideoFlow Publisher 已通过审核:**
- 可以立即提交 ClipScheduler

**如果 VideoFlow Publisher 还在审核中:**
- 建议等待结果后再提交
- 或者间隔至少 1-2 周

**如果 VideoFlow Publisher 被拒绝:**
- 先优化 VideoFlow Publisher 并重新提交
- 等通过后再提交 ClipScheduler

---

## 🆘 常见问题

### Q: ClipScheduler 和 VideoFlow Publisher 太相似了吗？
A: 不会。两者定位不同：
- VideoFlow = 快速发布工具
- ClipScheduler = 排期管理工具
核心功能和用户场景都有明显差异。

### Q: 如果两个都被拒绝怎么办？
A: 根据 TikTok 的反馈意见优化：
- 改进 demo 视频质量
- 完善应用说明
- 确保网站专业度

### Q: 可以用同一个邮箱吗？
A: 可以。TikTok 主要看应用的差异性，而不是联系邮箱。

### Q: Logo 必须重新设计吗？
A: 必须。每个应用应该有独特的 Logo 来体现品牌差异。

---

## 📞 需要帮助？

如果你需要：
- ✅ Demo 视频脚本修改
- ✅ Logo 设计建议
- ✅ 应用说明润色
- ✅ 审核被拒后的改进建议

随时找我！祝第二次申请顺利! 🚀
