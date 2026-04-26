# 🚀 Deployment Guide - NightFit Tracker

## Option 1: Vercel (Recommended - Free & Easy)

### Steps:
1. Push code to GitHub
2. Visit https://vercel.com
3. Click "Import Project"
4. Select your repo
5. Framework: Vite
6. Build: `npm run build`
7. Output: `dist`
8. Deploy! ✓

### Benefits:
- Free HTTPS
- PWA works perfectly
- Automatic deployments on push
- Global CDN

---

## Option 2: Netlify

### Steps:
1. Connect GitHub account at https://netlify.com
2. Create new site from Git
3. Select repository
4. Build command: `npm run build`
5. Publish directory: `dist`
6. Deploy ✓

### Benefits:
- Free SSL
- Form handling
- Analytics included
- Serverless functions

---

## Option 3: GitHub Pages

### Steps:
```bash
# Update vite.config.js
export default {
  base: '/nightfit-tracker/', // your repo name
  // ... rest of config
}

# Build
npm run build

# Deploy
git add dist/
git commit -m "Deploy"
git push origin main

# Enable Pages: Settings → Pages → Main branch /dist
```

---

## Option 4: Self-Hosted (VPS/Server)

### Steps:
```bash
# On your server
npm install
npm run build

# Copy dist/ to web root
cp -r dist/* /var/www/nightfit/

# Use nginx config below
```

### Nginx Configuration:
```nginx
server {
  listen 443 ssl http2;
  server_name nightfit.yoursite.com;

  ssl_certificate /etc/ssl/cert.pem;
  ssl_certificate_key /etc/ssl/key.pem;

  root /var/www/nightfit;
  
  # SPA routing
  location / {
    try_files $uri $uri/ /index.html;
  }

  # Cache static assets
  location ~* \.(js|css|png|jpg|svg|woff2)$ {
    expires 1y;
    add_header Cache-Control "public, immutable";
  }

  # Don't cache index.html
  location = /index.html {
    expires 0;
    add_header Cache-Control "public, max-age=0, must-revalidate";
  }

  # Enable gzip
  gzip on;
  gzip_types text/plain text/css application/json application/javascript;
}
```

---

## Environment Setup

### Development
```bash
npm run dev
# Visit http://localhost:5173
```

### Production Build
```bash
npm run build
# Creates /dist with everything ready

npm run preview
# Test production build locally
```

---

## PWA Testing Checklist

Before deploying:

✅ **Service Worker**
```
DevTools → Application → Service Workers
Should show "active" or "running"
```

✅ **Manifest**
```
DevTools → Application → Manifest
All required fields present
```

✅ **HTTPS**
- PWA requires HTTPS in production
- Self-signed ok for testing

✅ **Icon Generation**
- Icons should appear on home screen
- Check sizes: 192px, 512px

✅ **Offline Mode**
- Open DevTools → Network
- Check "Offline" checkbox
- App should still work

✅ **Install Prompt**
- iOS: Share → Add to Home Screen
- Android: Menu → Install App

---

## Performance Optimization

### Bundle Size
Current: ~45KB gzipped

```bash
# Analyze
npm run build -- --analyze
```

### Caching Strategy
- Assets: 1 year (versioned by build)
- HTML: No cache (always fresh)
- SW: Always refresh

### Load Time
- First load: <2s
- Repeat load: <500ms (cached)
- Offline: Instant (cached)

---

## Domain Setup

### DNS Records
```
A record: your-server-ip → nightfit.yoursite.com
AAAA record: ipv6 → nightfit.yoursite.com
```

### SSL Certificate
**Vercel/Netlify**: Automatic ✓

**Self-hosted**: Use Let's Encrypt
```bash
sudo certbot certonly -d nightfit.yoursite.com
# Renews automatically
```

---

## Monitoring & Analytics

### Check Service Worker Status
```javascript
navigator.serviceWorker.ready.then(r => {
  console.log('SW ready:', r);
})
```

### Monitor Cache Size
```javascript
caches.keys().then(names => {
  names.forEach(name => {
    caches.open(name).then(c => {
      c.keys().then(keys => {
        console.log(name, keys.length, 'files');
      });
    });
  });
});
```

### Check Installed Users
Google Play Console → Installs by Device Type

---

## Troubleshooting Deployment

### PWA not installing?
1. Check HTTPS is enabled
2. Verify manifest.json exists
3. Test with: `navigator.serviceWorker.ready`

### Data not persisting?
1. Check localStorage isn't disabled
2. Ensure quota isn't exceeded
3. Try private browsing mode

### Service Worker stuck?
1. DevTools → Clear site data
2. Uninstall and reinstall app
3. Hard refresh (Cmd+Shift+R)

### Build fails?
```bash
# Clear cache
rm -rf node_modules package-lock.json
npm install
npm run build
```

---

## Continuous Deployment (GitHub Actions)

Create `.github/workflows/deploy.yml`:

```yaml
name: Deploy to Vercel

on:
  push:
    branches: [main]

jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      
      - name: Install dependencies
        run: npm ci
      
      - name: Build
        run: npm run build
      
      - name: Deploy to Vercel
        uses: vercel/action@master
        with:
          vercel-token: ${{ secrets.VERCEL_TOKEN }}
          vercel-org-id: ${{ secrets.VERCEL_ORG_ID }}
          vercel-project-id: ${{ secrets.VERCEL_PROJECT_ID }}
```

---

## Post-Deployment Checklist

- [ ] App installs on iOS
- [ ] App installs on Android
- [ ] Offline mode works
- [ ] Data syncs correctly
- [ ] All features functional
- [ ] No console errors
- [ ] PWA appears in app store search
- [ ] Metrics/analytics tracking
- [ ] Performance <2s load time
- [ ] Mobile responsive tested

---

## Support

**Issues?** Contact: imranansani8@gmail.com

**Made with ❤️ by Md Emran Hasan**

⚡ **NightFit Tracker** - Smart Fitness for Night Shift Workers
