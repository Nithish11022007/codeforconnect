# JoinIn - SRM's Pulse

The "Just-in-Time" Connection Layer for SRM AP Campus. Eat together. Study together. Connect in real life.

## Quick Start

### 1. Firebase Setup

1. Go to [Firebase Console](https://console.firebase.google.com/)
2. Create a new project (e.g., "JoinIn")
3. Enable **Authentication** → Google Sign-In
4. Create a **Firestore Database**
5. Get your config from Project Settings → General → Your apps → Add web app
6. Copy config values to a `.env` file:

```
VITE_FIREBASE_API_KEY=...
VITE_FIREBASE_AUTH_DOMAIN=....firebaseapp.com
VITE_FIREBASE_PROJECT_ID=...
VITE_FIREBASE_STORAGE_BUCKET=....appspot.com
VITE_FIREBASE_MESSAGING_SENDER_ID=...
VITE_FIREBASE_APP_ID=...
```

### 2. Firestore Index

On first run, Firestore may prompt you to create a composite index. Click the link in the console error to auto-create it, or deploy:

```bash
firebase deploy --only firestore:indexes
```

### 3. Firestore Rules

Deploy rules:

```bash
firebase deploy --only firestore:rules
```

### 4. Run the App

```bash
npm install
npm run dev
```

Open `http://localhost:5173`

### 5. Domain Restriction

Only `@srmap.edu.in` emails can sign in. For testing, temporarily change `ALLOWED_DOMAIN` in `src/lib/firebase.js` or add test users in Firebase Auth.

## Tech Stack

- React + Vite
- Tailwind CSS
- Firebase (Auth + Firestore)
- Lucide React
- React Router

## Deploy to Vercel

1. Push to GitHub
2. Import project in Vercel
3. Add environment variables
4. Deploy
