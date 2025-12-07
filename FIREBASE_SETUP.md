# Firebase Real-Time Database Setup Guide
## GMC Sirsa Dashboard - Admin to Client Sync

### Problem Solved
When admin changes data via admin.html, the dashboard (index.html) on client devices now AUTOMATICALLY UPDATES IN REAL-TIME using Firebase.

### Quick Setup (5 minutes)

#### Step 1: Create Firebase Project
1. Go to Firebase Console (https://console.firebase.google.com)
2. Click Add Project
3. Name: gmc-sirsa (or any name)
4. Uncheck Enable Google Analytics (optional)
5. Click Create Project
6. Wait for project to be created

#### Step 2: Enable Realtime Database
1. Left sidebar > Realtime Database
2. Click Create Database
3. Select location: asia-southeast1 (Singapore is closest to India)
4. Choose Start in test mode (for development)
5. Click Enable

#### Step 3: Get Firebase Config
1. Left sidebar > Project Settings (gear icon)
2. Scroll down > Find Your apps section
3. Click </> Web (add Firebase to web app)
4. Copy the entire firebaseConfig object with all 7 keys

#### Step 4: Configure Dashboard
1. Open admin.html in browser
2. Open browser console (F12 > Console tab)
3. Copy-paste this command with YOUR Firebase values:

localStorage.setItem('firebaseApiKey', 'YOUR_API_KEY');
localStorage.setItem('firebaseAuthDomain', 'your-project.firebaseapp.com');
localStorage.setItem('firebaseDatabaseURL', 'https://your-project.firebaseio.com');
localStorage.setItem('firebaseProjectId', 'your-project-id');
localStorage.setItem('firebaseStorageBucket', 'your-project.appspot.com');
localStorage.setItem('firebaseMessagingSenderId', '123456789');
localStorage.setItem('firebaseAppId', '1:123456789:web:abc123def456');

4. Press Enter
5. Reload the page

#### Step 5: Test Admin Panel
1. Go to admin.html
2. Password: admin123
3. Update any field
4. Click Save All Changes to Dashboard
5. You should see green message: Data saved successfully!

#### Step 6: Test Real-Time Sync
1. Open index.html in another tab/window
2. Dashboard shows your saved data
3. Go back to admin.html and change values
4. Dashboard auto-updates in real-time (every 5 seconds)

### Give Link to Client
Now share this dashboard link with your client:
https://pankajkapil.github.io/gmc-sirsa-dashboard/index.html

Every admin update automatically syncs to the client dashboard!

### Troubleshooting
- Dashboard not updating? Clear cache and reload
- Firebase errors? Check config keys in localStorage
- Admin save failing? Check browser console for errors

---
Setup Date: 7 Dec 2025
