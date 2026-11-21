# Study Compass — v1.0

An original responsive study planner. No build process, external libraries, login, analytics or ads.

## Features
- Dashboard with daily focus goal and upcoming work.
- Add/edit/complete/delete tasks; subjects, priorities, due dates and filters.
- Focus timer and two break modes; adjustable durations; completed sessions recorded once.
- Exam countdowns; add/edit/delete exams.
- Searchable notes with editing.
- Seven-day focus chart, completion statistics and session history.
- Dark theme; JSON export/import with validation; local data deletion.
- Installable web manifest, PNG icons and offline service-worker cache.

## GitHub Pages
1. Unzip. Upload the CONTENTS of StudyCompass directly to your repository root; index.html must be at the root. No npm install or build required.
2. Settings → Pages → deploy from branch → main / root → Save.
3. Visit the resulting HTTPS URL. All paths are relative, including for repository subpaths.
4. Open once online, allow the service worker to activate, then reload before testing offline.
5. When changing releases, update the CACHE version in sw.js.

## Local preview
Run `python3 -m http.server 8080` in this folder, then open http://localhost:8080. Opening index.html directly is not a full PWA/offline test.

## Important behavior
Browser storage is per origin/device and is not a cloud backup. Back up regularly. Background timers can be suspended by Android/the browser; the app reconciles elapsed time when reopened while the page remains alive. Closing/reloading the page cancels an unfinished timer; it does not count as completed. Keep the app open for reliable sessions. No push reminders or background alarm guarantee is claimed.

## Android Studio / release handoff
This ZIP is the web source, not an Android Studio project or signed AAB. The final Android app needs a correctly configured wrapper, launcher assets, signing and a signed Android App Bundle. Website hosting alone does not package the Android app.
- Enable JavaScript and DOM storage only for your own trusted app origin. Keep HTTPS and handle network failures/back navigation cleanly.
- To support exports, implement Blob download handling in the native wrapper (or offer external-browser export); Android WebView does not automatically download Blob URLs. Implement the file chooser for JSON restore.
- Test timer lifecycle, navigation, keyboard, local storage, backup and accessibility on physical Android devices. Offline service-worker behavior must be tested in the chosen wrapper; bundling local assets with WebViewAssetLoader is another option requiring Android implementation.
- Request only permissions actually required. Current web features do not need sensitive permissions.
- Add your developer name and support email to privacy.html before publishing; host the policy at a publicly accessible URL.
- Complete Play Console privacy/Data Safety, content rating, audience and testing requirements accurately for the FINAL Android package, including any SDKs. Verify current target API and release requirements at submission.
- Google Play approval is not guaranteed by this template or its feature count. Do not claim notifications, cross-device sync or guaranteed background tracking.

## Included files
index.html, style.css, app.js, sw.js, manifest.webmanifest, icon.svg, icon-192.png, icon-512.png, privacy.html, README.md, .nojekyll.

The artwork and code are included for use and modification in your app.
