# AI DevTools Hub

A curated directory of AI tools for developers, designers, and PMs, with rankings, ratings, search, category and job-role filters, and bookmarks. It ships as a regular website and also installs as a mobile app (PWA) on Android, iPhone/iPad, and desktop.

## Technologies
- Static HTML + vanilla JavaScript (`public/index.html`)
- Tailwind CSS (CDN), Pretendard font, Font Awesome icons
- Progressive Web App: `manifest.webmanifest` + service worker (`sw.js`) for installation and offline use
- Hosted on Netlify

## Installing the mobile app
- Use the **앱 설치** button in the header, the install section at the bottom of the page, or the footer link.
- Share the short link `https://<your-site>/install` (or the QR code shown on the page). It opens the install guide straight away.
- Android/desktop Chrome & Edge: one-click install. iOS Safari: Share → Add to Home Screen (step-by-step guide included).

## Running locally
No build step is needed. Serve the `public` folder, for example:

```bash
netlify dev --port 8889
# or
npx serve public
```
