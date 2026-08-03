# health-water-schedule

## 🚀 Complete Deployment & Setup Guide

This tracker relies on your browser's local storage and is designed to run entirely client-side without a backend database. Follow these exact steps to host it for free on GitHub Pages and configure the native mobile integrations.

---

### Phase 1: Repository Setup
To make this a fully functional Progressive Web App (PWA), you must create and upload the following files to a new public repository on your GitHub account. Ensure all files are placed in the root directory.

**1. `index.html`**
* This is your core application file containing all the HTML, CSS, and JavaScript logic.

**2. `manifest.json`**
* This configuration file tells your phone how the app should look and behave when saved to the home screen (e.g., dictating the app name, standalone display mode, and theme colors).

**3. App Icons (`icon-192.png` and `icon-512.png`)**
* Generate or download a simple square icon (e.g., a water drop or checkmark) in PNG format.
* Upload two versions to the repository named exactly `icon-192.png` (192x192 pixels) and `icon-512.png` (512x512 pixels).

**4. `sw.js` (The Service Worker)**
* This JavaScript file runs in the background and caches your web assets. This is what allows the application to open instantly and function even when your device is offline or in airplane mode.

---

### Phase 2: Deploy to GitHub Pages
Once all files are uploaded to your repository, turn the repository into a live website:

1. Navigate to your repository on GitHub.
2. Click the **Settings** tab near the top right of the screen.
3. On the left sidebar, scroll down and click **Pages**.
4. Under the **Build and deployment** section, locate the **Branch** dropdown menu.
5. Change the branch from `None` to **main** (or `master`, depending on your default).
6. Leave the folder selector as `/ (root)`.
7. Click **Save**.
8. Wait 1-3 minutes. Refresh the page, and GitHub will provide your live URL (e.g., `https://[your-username].github.io/[repo-name]`).

---

### Phase 3: Apple Health Integration (iOS Only)
Apple blocks web browsers from writing directly to HealthKit. To bypass this, the tracker uses a deep link to trigger an iOS Shortcut. You must configure this exact shortcut on your iPhone:

1. Open the **Shortcuts** app on your iPhone.
2. Tap the **+** in the top right to create a new shortcut.
3. Tap the name at the top to rename it. Name it exactly **LogWater** (case-sensitive, absolutely no spaces).
4. Tap **Add Action** and search for **Log Health Sample**.
5. Tap the action to add it. 
6. Set the Type to **Water**.
7. Tap the **Value** field, and select **Shortcut Input** from the variables above the keyboard.
8. Tap where it says "Shortcut Input" and ensure the input type is set to **Number**.
9. Tap **Done** to save the shortcut.

*Now, when you tap the sync button in the web app, Safari will briefly open Shortcuts, write the exact milliliter amount to Apple Health, and return to your tracker.*

---

### Phase 4: Mobile Installation (Standalone App)
To remove the Safari/Chrome search bar and make this behave like a native application:

1. Open your live GitHub Pages link on your phone's browser.
2. On **iOS (Safari)**: Tap the Share button (the square with the up arrow) at the bottom.
3. On **Android (Chrome)**: Tap the three-dot menu at the top right.
4. Scroll down and tap **Add to Home Screen**.
5. Close your browser and launch the app from the new icon on your home screen.
