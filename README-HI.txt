FINANCE TRACKER PWA PACKAGE

Files:
- index.html: your current Finance Tracker with PWA metadata/registration added
- manifest.webmanifest: install name, icon and standalone display settings
- sw.js: caches the app shell for offline reopening
- icons/: home-screen icons

IMPORTANT LIMITATIONS
1. A PWA must be hosted over HTTPS (or localhost) to install/service-worker cache. Opening index.html directly from a file manager will not install it as a PWA.
2. The existing HTML loads Tailwind CSS, Font Awesome and Chart.js from external CDNs. This package cannot bundle those libraries because the build environment has no internet access. Therefore, after first visit the app shell can be cached, but complete offline styling/icons/charts are NOT guaranteed until those libraries are bundled locally.
3. Browser localStorage is isolated by origin. Installing this hosted PWA will not automatically see data saved by the old file/browser origin. Before switching, open your current app and use its built-in Backup/Export feature; then restore/import that backup in the hosted PWA if the app's restore feature supports it. Do not clear browser data or uninstall the old copy until you verify all records.
4. Keep encrypted/private backups safe; this app stores financial records locally unless you separately configure a sync service.

ANDROID INSTALL STEPS
1. Upload the contents of this folder to a static HTTPS host (not the ZIP itself). Keep index.html, manifest.webmanifest, sw.js, and icons/ at the same paths.
2. On Android, open the HTTPS URL in Chrome while online and wait for it to finish loading.
3. In Chrome menu (⋮), choose “Install app” or “Add to Home screen” if offered.
4. Launch from the new icon. Open it online once so the service worker can cache the app shell.
5. Test offline with airplane mode. Because the app references external CDNs, some appearance/chart features may still require internet until the libraries are bundled locally.
