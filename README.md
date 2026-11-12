# Bosman-Clothing: Tailor's Pouch setup

## 1. Put the app online (GitHub Pages)
1. Open https://github.com/tailorspouch/Bosman-Clothing, click **Add file > Upload files**.
2. Upload ALL files: index.html, manifest.json, sw.js and the four icon PNGs. Click **Commit changes**.
3. Go to **Settings > Pages**, set Source to **Deploy from a branch**, branch **main**, folder **/ (root)**, Save.
4. After a minute your app is at https://tailorspouch.github.io/Bosman-Clothing/

## 2. Firebase (project bosmanclothing-5c2bd)
1. **Build > Authentication > Get started > Email/Password > Enable.**
2. **Authentication > Settings > Authorized domains > Add domain:** `tailorspouch.github.io`
3. **Authentication > Users > Add user:** create the admin (thesamueloseni@gmail.com) and owner (bosmanclothings@gmail.com) accounts with passwords. Only these two are made by hand; staff are added inside the app (Admin button).
4. **Build > Firestore Database > Create database** (production mode).
5. **Firestore > Rules:** paste everything from firestore-rules.txt, click **Publish**.

## 3. Test
1. Open the link in Chrome on your phone, sign in as admin, add a client, tap **Sync**.
2. Add a staff member in **Admin**. Sign in as them on another phone; they set their own password on first sign-in.
3. Turn on airplane mode and reopen the app: it still works (sign in online once first).

## 4. Install
Chrome shows an **Install app** button on the sign-in and home screens. If not, use Chrome menu (⋮) > **Install app**. Use **Check for update** after uploading new files.

## Chrome DevTools check (on a computer)
F12 > **Application**: Manifest (no errors, 4 icons), Service Workers (activated and running). **Lighthouse** > PWA/Installable > run.

## 5. Google Drive backup (one-time)
1. console.cloud.google.com > create a project > **APIs & Services > Library > Google Drive API > Enable**.
2. **OAuth consent screen**: External, add your Gmail as a test user.
3. **Credentials > Create credentials > OAuth client ID > Web application**. Under Authorized JavaScript origins add `https://tailorspouch.github.io`. Copy the Client ID.
4. In the app tap **Drive backup**, paste the Client ID, sign in and tick the Google Drive box. Reconnect is asked about once an hour.

**Drive note:** the Google Client ID is already built into the app. In Google Cloud add `https://tailorspouch.github.io` under Authorized JavaScript origins, and add every Gmail you want to back up to as a test user. In the app: **Drive > Add Google account** (repeat for more accounts), then **Back up now** per account.
**EmailJS (optional):** create a free emailjs.com service and template using the variables `to_email`, `subject`, `message`. In Finance > Weekly/Monthly report tap **Email report** and enter the IDs once.
