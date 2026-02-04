# ClipScheduler OAuth Login Integration 🔐

## 🚀 Quick Start (3 Minutes)

### Step 1: Get Your Client Key
1. Visit: https://developers.tiktok.com/
2. Navigate to your app (ClipScheduler)
3. Copy the Client Key (starts with `aw`)

### Step 2: Configure Client Key
1. Open `index.html`
2. Find line 240:
   ```javascript
   const TIKTOK_CLIENT_KEY = 'YOUR_CLIENT_KEY_HERE';
   ```
3. Replace with your actual Client Key:
   ```javascript
   const TIKTOK_CLIENT_KEY = 'awYourActualClientKey';
   ```

### Step 3: Upload to GitHub
1. Visit: https://github.com/this-ZZHXD/clipscheduler-policies
2. Replace the existing `index.html`
3. Replace the existing `callback.html`
4. Wait 2-3 minutes for deployment

### Step 4: Test
1. Visit: https://this-ZZHXD.github.io/clipscheduler-policies/
2. Click "Get Started"
3. Should redirect to TikTok authorization page ✅

---

## ✨ Key Features

### index.html
- ✅ Complete OAuth 2.0 login flow
- ✅ Secure state token generation (CSRF protection)
- ✅ Configuration validation with warnings
- ✅ Login state detection
- ✅ Beautiful, responsive UI

### callback.html
- ✅ Handles OAuth callback
- ✅ Three display states (success/error/no-params)
- ✅ State token security verification
- ✅ Authorization details display
- ✅ Session management functions

---

## 📋 Configuration Checklist

```
[ ] Obtained TikTok Client Key
[ ] Configured Client Key in index.html
[ ] Uploaded index.html to GitHub
[ ] Uploaded callback.html to GitHub
[ ] Waited 2-3 minutes for GitHub Pages deployment
[ ] Tested "Get Started" button redirects to TikTok
[ ] Successfully returned to callback page after authorization
[ ] Callback page shows success state
```

---

## 🔧 Important Configuration

### Redirect URI (Must Match Exactly)
```
https://this-ZZHXD.github.io/clipscheduler-policies/callback.html
```

**Must be identical in both places:**
1. TikTok Developer Portal Login Kit configuration
2. `REDIRECT_URI` constant in index.html

### Scopes (Permissions)
```
user.info.basic,video.upload,video.publish
```

**What each scope does:**
- `user.info.basic` - Access user profile and display name
- `video.upload` - Upload videos to TikTok
- `video.publish` - Publish scheduled videos automatically

---

## 🎯 OAuth Flow

```
User clicks "Get Started"
    ↓
Generate state token
    ↓
Redirect to TikTok authorization page
    ↓
User logs in and authorizes
    ↓
TikTok redirects back to callback.html
    ↓
Verify state token
    ↓
Display authorization success
```

---

## 🚨 Troubleshooting

### Q: Button doesn't respond when clicked?
**A:** Check if Client Key is properly configured. Open browser console (F12) to see errors.

**Debug in console:**
```javascript
console.log(TIKTOK_CLIENT_KEY);
// Should show your actual key, not 'YOUR_CLIENT_KEY_HERE'
```

---

### Q: "Invalid client_key" error after redirect?
**A:** Client Key is incorrect. Ensure:
- No extra spaces before or after the key
- Properly wrapped in single quotes
- Completely copied from TikTok Developer Portal

**Correct format:**
```javascript
const TIKTOK_CLIENT_KEY = 'aw12345678901234567';
```

**Incorrect formats:**
```javascript
const TIKTOK_CLIENT_KEY = ' aw12345678901234567 ';  // ❌ Has spaces
const TIKTOK_CLIENT_KEY = aw12345678901234567;      // ❌ Missing quotes
```

---

### Q: "Redirect URI mismatch" error?
**A:** Redirect URI configuration doesn't match between TikTok Portal and your code.

**Verify both locations:**

**In index.html (line ~241):**
```javascript
const REDIRECT_URI = 'https://this-ZZHXD.github.io/clipscheduler-policies/callback.html';
```

**In TikTok Developer Portal:**
```
Login Kit → Redirect URI:
https://this-ZZHXD.github.io/clipscheduler-policies/callback.html
```

**Must be exactly the same!**

---

### Q: "State mismatch" error in callback?
**A:** Session storage was cleared or you're using a different tab.

**Solutions:**
- Start the authorization flow again
- Complete the entire process in the same browser tab
- Disable privacy/incognito mode (sessionStorage may be restricted)

---

## 🎓 Technical Details

### Security Features

**1. CSRF Protection**
```javascript
// Generate random state token
const state = generateRandomState();

// Save to sessionStorage
sessionStorage.setItem('tiktok_oauth_state', state);

// Verify on callback
const savedState = sessionStorage.getItem('tiktok_oauth_state');
if (receivedState !== savedState) {
    // Reject - possible CSRF attack
}
```

**2. Session Isolation**
- Uses `sessionStorage` (auto-clears when tab closes)
- No sensitive data in URL parameters
- Authorization code only stored temporarily

**3. Error Handling**
- Catches all possible errors
- Provides clear error messages
- Prevents sensitive information leakage

---

### Browser Compatibility
- ✅ Chrome/Edge (recommended)
- ✅ Firefox
- ✅ Safari
- ✅ Mobile browsers

---

## 📖 Code Structure

### index.html Key Functions

**OAuth Redirect:**
```javascript
function loginWithTikTok() {
    // 1. Validate configuration
    if (TIKTOK_CLIENT_KEY === 'YOUR_CLIENT_KEY_HERE') {
        showConfigWarning();
        return;
    }
    
    // 2. Generate state token
    const state = generateRandomState();
    
    // 3. Save state for verification
    sessionStorage.setItem('tiktok_oauth_state', state);
    
    // 4. Build authorization URL
    const authUrl = 'https://www.tiktok.com/v2/auth/authorize/' +
        '?client_key=' + encodeURIComponent(TIKTOK_CLIENT_KEY) +
        '&scope=' + encodeURIComponent(SCOPES) +
        '&response_type=code' +
        '&redirect_uri=' + encodeURIComponent(REDIRECT_URI) +
        '&state=' + encodeURIComponent(state);
    
    // 5. Redirect to TikTok
    window.location.href = authUrl;
}
```

**State Generation:**
```javascript
function generateRandomState() {
    const chars = 'ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789';
    let state = '';
    for (let i = 0; i < 32; i++) {
        state += chars.charAt(Math.floor(Math.random() * chars.length));
    }
    return state;
}
```

---

### callback.html Key Functions

**Parse URL Parameters:**
```javascript
function getUrlParams() {
    const params = new URLSearchParams(window.location.search);
    return {
        code: params.get('code'),
        state: params.get('state'),
        error: params.get('error'),
        error_description: params.get('error_description'),
        scopes: params.get('scopes')
    };
}
```

**Verify State:**
```javascript
function verifyState(receivedState) {
    const savedState = sessionStorage.getItem('tiktok_oauth_state');
    
    if (!savedState) {
        console.warn('No saved state found');
        return false;
    }
    
    if (receivedState !== savedState) {
        console.error('State mismatch - possible CSRF attack');
        return false;
    }
    
    return true;
}
```

**Handle Success:**
```javascript
function handleSuccess(params) {
    // Verify state token
    if (!verifyState(params.state)) {
        handleError({ 
            error: 'state_mismatch',
            error_description: 'State verification failed'
        });
        return;
    }
    
    // Display success UI
    showSuccessState();
    
    // Save authorization code
    sessionStorage.setItem('tiktok_auth_code', params.code);
    
    // Clear OAuth state
    sessionStorage.removeItem('tiktok_oauth_state');
}
```

---

## 🔄 Next Steps

After implementing OAuth, you can:

### 1. Exchange Code for Access Token
**Backend required (secure):**
```javascript
// This happens on your server, not in browser
const response = await fetch('https://open.tiktokapis.com/v2/oauth/token/', {
    method: 'POST',
    headers: { 'Content-Type': 'application/x-www-form-urlencoded' },
    body: new URLSearchParams({
        client_key: CLIENT_KEY,
        client_secret: CLIENT_SECRET,  // Never expose in frontend!
        code: authorizationCode,
        grant_type: 'authorization_code',
        redirect_uri: REDIRECT_URI
    })
});

const { access_token, refresh_token } = await response.json();
```

### 2. Call TikTok APIs
**With access token:**
```javascript
// Get user info
const userInfo = await fetch('https://open.tiktokapis.com/v2/user/info/', {
    headers: {
        'Authorization': `Bearer ${access_token}`
    }
});

// Upload video
const upload = await fetch('https://open.tiktokapis.com/v2/post/publish/video/init/', {
    method: 'POST',
    headers: {
        'Authorization': `Bearer ${access_token}`,
        'Content-Type': 'application/json'
    },
    body: JSON.stringify({
        post_info: {
            title: 'My Video Title',
            privacy_level: 'SELF_ONLY',  // Sandbox limitation
            disable_duet: false,
            disable_comment: false,
            disable_stitch: false,
            video_cover_timestamp_ms: 1000
        },
        source_info: {
            source: 'FILE_UPLOAD',
            video_size: videoFile.size,
            chunk_size: 10000000,
            total_chunk_count: 1
        }
    })
});
```

### 3. Build Your Application
- Create calendar interface
- Implement video scheduling
- Add bulk upload feature
- Set up automated publishing

---

## 📱 Demo Features

### What Works Now:
- ✅ OAuth login flow
- ✅ State verification
- ✅ Authorization code retrieval
- ✅ Error handling
- ✅ Session management

### What Needs Implementation:
- ⏳ Backend server for token exchange
- ⏳ Access token storage
- ⏳ API calls to TikTok
- ⏳ Video upload functionality
- ⏳ Scheduling system

---

## 📞 Need Help?

### Getting Support:
1. Check browser console for errors (F12)
2. Verify Client Key is correctly configured
3. Ensure Redirect URI matches exactly
4. Review the detailed documentation (Chinese guides included)

### Useful Links:
- **TikTok Developer Docs:** https://developers.tiktok.com/doc/
- **OAuth 2.0 Guide:** https://developers.tiktok.com/doc/login-kit-web
- **API Reference:** https://developers.tiktok.com/doc/content-posting-api-get-started

---

## 🎉 Getting Started

**Configure in 3 minutes:**

1. Get your Client Key from TikTok Developer Portal
2. Configure `TIKTOK_CLIENT_KEY` in index.html
3. Upload both files to GitHub
4. Test the login flow

**That's it!** 🚀

---

## 📄 License

ClipScheduler is a demonstration project for TikTok Content Posting API integration.

---

## 🌟 Features Highlight

### User Experience
- Clean, modern interface with gradient theme
- Responsive design for all devices
- Clear status indicators
- Helpful error messages

### Security
- CSRF protection with state tokens
- Secure session management
- Input validation
- Error boundary handling

### Developer Experience
- Well-commented code
- Modular function design
- Console logging for debugging
- Easy to customize and extend

---

**Happy coding!** 🎊

For detailed Chinese documentation, see:
- OAuth功能使用说明.md (Complete guide)
- 快速配置清单.md (Quick start)
