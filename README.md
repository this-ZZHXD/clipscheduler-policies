# ClipScheduler OAuth 登录功能 🔐

## 📦 文件清单

本文件夹包含完整的 OAuth 登录功能代码：

```
clipscheduler_oauth_files/
├── index.html                  - 主页（带 OAuth 登录功能）
├── callback.html               - OAuth 回调处理页面
├── OAuth功能使用说明.md        - 详细配置和使用文档
├── 快速配置清单.md             - 3 分钟快速配置指南
└── README.md                   - 本文件
```

---

## 🚀 快速开始（3 分钟）

### 步骤 1：获取 Client Key
1. 访问：https://developers.tiktok.com/
2. 进入你的应用（ClipScheduler）
3. 复制 Client Key（以 `aw` 开头）

### 步骤 2：配置 Client Key
1. 打开 `index.html`
2. 找到第 240 行：
   ```javascript
   const TIKTOK_CLIENT_KEY = 'YOUR_CLIENT_KEY_HERE';
   ```
3. 替换成你的 Client Key：
   ```javascript
   const TIKTOK_CLIENT_KEY = 'aw你的实际ClientKey';
   ```

### 步骤 3：上传到 GitHub
1. 访问：https://github.com/this-ZZHXD/clipscheduler-policies
2. 替换旧的 `index.html`
3. 替换旧的 `callback.html`
4. 等待 2-3 分钟

### 步骤 4：测试
1. 访问：https://this-ZZHXD.github.io/clipscheduler-policies/
2. 点击 "Get Started"
3. 应该跳转到 TikTok 授权页面 ✅

---

## ✨ 主要功能

### index.html
- ✅ 真实的 OAuth 登录流程
- ✅ 安全的 state token 生成
- ✅ 配置检查和错误提示
- ✅ 登录状态检测
- ✅ 美观的用户界面

### callback.html
- ✅ 处理 OAuth 回调
- ✅ 三种状态显示（成功/失败/无参数）
- ✅ State token 安全验证
- ✅ 授权信息展示
- ✅ 会话管理功能

---

## 📋 配置检查清单

```
[ ] 已获取 TikTok Client Key
[ ] 已在 index.html 中配置 Client Key
[ ] 已上传 index.html 到 GitHub
[ ] 已上传 callback.html 到 GitHub
[ ] 已等待 2-3 分钟（GitHub Pages 部署）
[ ] 测试点击 "Get Started" 能跳转到 TikTok
[ ] 授权后能返回 callback 页面
[ ] callback 页面显示成功状态
```

---

## 🔧 重要配置

### Redirect URI（必须匹配）
```
https://this-ZZHXD.github.io/clipscheduler-policies/callback.html
```

**在这两个地方必须完全一致：**
1. TikTok Developer Portal 的 Login Kit 配置
2. index.html 中的 `REDIRECT_URI` 常量

### Scopes（权限）
```
user.info.basic,video.upload,video.publish
```

---

## 🎯 OAuth 流程

```
用户点击 "Get Started"
    ↓
生成 state token
    ↓
跳转到 TikTok 授权页面
    ↓
用户登录并授权
    ↓
TikTok 重定向回 callback.html
    ↓
验证 state token
    ↓
显示授权成功
```

---

## 🚨 常见问题

### Q: 点击按钮没反应？
**A:** 检查 Client Key 是否正确配置，打开浏览器控制台（F12）查看错误

### Q: 显示 "Invalid client_key"？
**A:** Client Key 填写错误，重新复制正确的 Client Key

### Q: 显示 "Redirect URI mismatch"？
**A:** Redirect URI 配置不一致，检查 TikTok Portal 和代码中的配置

---

## 📖 详细文档

- **OAuth功能使用说明.md** - 完整的配置和使用指南
- **快速配置清单.md** - 3 分钟快速开始

---

## 🎓 技术细节

### 安全特性
- ✅ CSRF 防护（state token）
- ✅ 会话隔离（sessionStorage）
- ✅ 错误处理和验证

### 浏览器兼容性
- ✅ Chrome/Edge（推荐）
- ✅ Firefox
- ✅ Safari
- ✅ 移动浏览器

---

## 📞 需要帮助？

查看详细文档或检查：
- 浏览器控制台错误信息
- Client Key 配置是否正确
- Redirect URI 是否匹配
- GitHub Pages 是否已部署

---

## 🎉 开始使用

**现在就配置吧！只需 3 分钟！**

1. 配置 Client Key
2. 上传文件
3. 测试登录
4. 完成！

祝你使用愉快！🚀
