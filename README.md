# ClipScheduler - TikTok API Application Website

## Overview
This website is created for applying to TikTok's Content Posting API.

**Application Type:** Scheduling Tools  
**GitHub Pages URL:** https://this-ZZHXD.github.io/clipscheduler-policies/  
**TikTok Developer Account:** ZZH_Workspace

## Files Included
- `index.html` - Main landing page
- `terms-of-service.html` - Terms of Service
- `privacy-policy.html` - Privacy Policy  
- `callback.html` - OAuth callback handler
- `CS.jpg` - Application logo (placeholder)
- `README.md` - This file

## Application Description
Advanced scheduling and calendar management for TikTok content creators

## Key Features
- Visual Calendar: See your entire content schedule at a glance with calendar view
- Smart Timing: AI-powered suggestions for optimal posting times based on your audience
- Bulk Upload: Upload multiple videos at once and schedule them in advance
- Recurring Posts: Set up recurring content series with automatic scheduling
- Time Zone Support: Schedule posts for different time zones to reach global audiences
- Draft Management: Save video drafts and schedule them for future publication

## API Scopes Required
- `user.info.basic` - Display TikTok profile information
- `video.upload` - Upload video files to TikTok
- `video.publish` - Publish videos to user's TikTok account

## Deployment Instructions

### 1. Create GitHub Repository
```bash
# Create new repository named: clipscheduler-policies
# Set to Public
```

### 2. Upload Files
Upload all files to the repository root:
- index.html
- terms-of-service.html
- privacy-policy.html
- callback.html
- CS.jpg
- README.md

### 3. Enable GitHub Pages
1. Go to Repository Settings
2. Navigate to "Pages" section
3. Source: Deploy from main branch
4. Save

### 4. Verify Deployment
Visit: https://this-ZZHXD.github.io/clipscheduler-policies/

### 5. TikTok Developer Portal Configuration

#### Basic Information
- App Name: ClipScheduler
- Platform: Web
- Website URL: https://this-ZZHXD.github.io/clipscheduler-policies/

#### Products
1. **Login Kit**
   - Redirect URI: https://this-ZZHXD.github.io/clipscheduler-policies/callback.html

2. **Content Posting API**
   - Enable "Direct Post"

#### Scopes
- [x] user.info.basic
- [x] video.upload
- [x] video.publish

#### App Review
**Explanation Text:**
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

**Demo Video:**
- Create a 3-5 minute video demonstrating the OAuth flow and video publishing workflow
- Show the website URL in browser
- Demonstrate all three scopes in action

## Next Steps After Approval
1. Receive Client Key and Client Secret
2. Implement OAuth flow
3. Build video upload functionality
4. Test in Sandbox mode
5. Apply for API Client Audit (for public posting)

## Contact
Email: support@clipschedulerpolicies.com

---
Generated: February 02, 2026
Application ID: app03
