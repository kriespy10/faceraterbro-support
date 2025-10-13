# FaceRaterBro Support Website

This is a simple support landing page that deep links back to the FaceRaterBro mobile app's Contact Support section.

## Features

- **Deep Linking**: When users click "Open Support in App", it will:
  1. Try to open the FaceRaterBro app with the URL scheme `faceraterbro://support`
  2. Navigate directly to the Contact Support screen in the app
  3. If the app is not installed, offer to redirect to the App Store

- **Contact Information**: Displays alternative contact methods including:
  - Email: support@faceraterbro.com
  - Response time information
  - List of support topics

## Setup Instructions

### 1. Update App Store URL

Before deploying, update line 193 in `index.html` with your actual App Store app ID:

```javascript
const fallbackUrl = 'https://apps.apple.com/app/faceraterbro/id<YOUR_APP_ID>';
```

Replace `<YOUR_APP_ID>` with your actual App Store ID (you'll get this after your app is approved).

### 2. Set Up Email Forwarding

Make sure you have `support@faceraterbro.com` set up and forwarding to your actual support email address.

### 3. Deploy to faceraterbro.com

You can deploy this static website to faceraterbro.com using any of these methods:

#### Option A: GitHub Pages
1. Create a GitHub repository for your website
2. Push the `support-website` folder contents
3. Enable GitHub Pages in repository settings
4. Point your domain `faceraterbro.com` to GitHub Pages

#### Option B: Vercel (Recommended - Fast & Free)
1. Install Vercel CLI: `npm i -g vercel`
2. Navigate to the support-website folder
3. Run: `vercel`
4. Follow the prompts
5. Add your custom domain in Vercel dashboard

#### Option C: Netlify
1. Drag and drop the support-website folder to [Netlify Drop](https://app.netlify.com/drop)
2. Add your custom domain in site settings

#### Option D: Traditional Web Hosting
1. Upload `index.html` to your web server via FTP/cPanel
2. Ensure it's accessible at `https://faceraterbro.com/`

### 4. Update App Store Connect

Once deployed:
1. Go to App Store Connect
2. Navigate to your app
3. Update the Support URL to: `https://faceraterbro.com/`
4. Save and resubmit your app

## Testing

### Test on iOS Device:
1. Make sure your app is installed
2. Open Safari and navigate to `https://faceraterbro.com/`
3. Click "Open Support in App"
4. The app should open and navigate to Contact Support

### Test Deep Link Directly:
1. Open Safari on iOS
2. Type: `faceraterbro://support`
3. Press Go
4. App should open to Contact Support

## Troubleshooting

### Deep link not working?
- Ensure the app URL scheme is properly configured in `app.json`:
  ```json
  "scheme": "faceraterbro"
  ```
- Make sure you've rebuilt the app with the latest changes
- Check that the app is installed on the device

### App not opening?
- Clear Safari cache and try again
- Ensure the app has been installed from TestFlight or App Store
- Check device logs for any deep link errors

## Files

- `index.html` - Main support page with deep linking functionality
- `README.md` - This file

## Support Page URL Structure

The support page URL should be:
- Production: `https://faceraterbro.com/` or `https://www.faceraterbro.com/`
- Staging (optional): `https://support.faceraterbro.com/`

## Maintenance

Remember to:
- Keep the email address updated
- Update response times if they change
- Add FAQ links as your Help & FAQ section grows
- Update the App Store URL once your app is live
