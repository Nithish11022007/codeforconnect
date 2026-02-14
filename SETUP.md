# JoinIn - Quick Setup Guide

## ✅ Already done for you
- `.env` file created (you need to add your Firebase config)
- Email allowed: **@srmap.edu.in** and **@gmail.com** (for online testing)
- Firebase config files (`firebase.json`, `.firebaserc`) added

---

## You must do these (one-time):

### 1. Add Firebase config to `.env`

1. Go to [Firebase Console](https://console.firebase.google.com/)
2. Select your project (or create one)
3. Click **⚙️ Project settings** → scroll to **Your apps**
4. Click the **</>** (web) icon → Register app → copy the config
5. Open `joinin-app/.env` and replace the placeholders:

```
VITE_FIREBASE_API_KEY=paste_your_api_key_here
VITE_FIREBASE_AUTH_DOMAIN=your-project.firebaseapp.com
VITE_FIREBASE_PROJECT_ID=your-project-id
VITE_FIREBASE_STORAGE_BUCKET=your-project.appspot.com
VITE_FIREBASE_MESSAGING_SENDER_ID=123456789
VITE_FIREBASE_APP_ID=1:123:web:abc...
```

### 2. Firebase Console setup
- **Authentication** → Enable **Google** sign-in
- **Firestore** → Create database (test mode for now)
- **Authentication** → **Settings** → **Authorized domains** → add `localhost`

### 3. Link Firebase project (for deploy)

```bash
cd joinin-app
npx firebase use YOUR_PROJECT_ID
```

Replace `YOUR_PROJECT_ID` with your project ID from Firebase Console.

### 4. Deploy Firestore rules (optional)

```bash
npx firebase deploy --only firestore
```

### 5. Run the app

```bash
cd joinin-app
npm run dev
```

Open **http://localhost:5173/** and sign in with **Gmail** or **@srmap.edu.in**.
