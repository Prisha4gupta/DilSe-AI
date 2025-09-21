# Firebase Setup Instructions

## 1. Create a Firebase Project

1. Go to [Firebase Console](https://console.firebase.google.com/)
2. Click "Create a project" or "Add project"
3. Enter project name: "dilse-ai" (or your preferred name)
4. Enable Google Analytics (optional)
5. Click "Create project"

## 2. Enable Authentication

1. In your Firebase project, go to "Authentication" in the left sidebar
2. Click "Get started"
3. Go to "Sign-in method" tab
4. Enable "Email/Password" authentication
5. Enable "Google" authentication (optional)

## 3. Get Firebase Configuration

1. Go to Project Settings (gear icon)
2. Scroll down to "Your apps" section
3. Click "Add app" and select Web (</>) icon
4. Register your app with a nickname
5. Copy the Firebase configuration object

## 4. Update Environment Variables

Add these to your `.env.local` file:

```env
# Existing Gemini API key
GEMINI_API_KEY=your_gemini_api_key_here

# Firebase Configuration
NEXT_PUBLIC_FIREBASE_API_KEY=your_api_key_here
NEXT_PUBLIC_FIREBASE_AUTH_DOMAIN=your_project_id.firebaseapp.com
NEXT_PUBLIC_FIREBASE_PROJECT_ID=your_project_id
NEXT_PUBLIC_FIREBASE_STORAGE_BUCKET=your_project_id.appspot.com
NEXT_PUBLIC_FIREBASE_MESSAGING_SENDER_ID=your_sender_id
NEXT_PUBLIC_FIREBASE_APP_ID=your_app_id
```

## 5. Test the Setup

1. Run `npm run dev`
2. Go to `/signup` and create a test account
3. Go to `/login` and sign in
4. Test the chat functionality at `/chat`

## Features Implemented

✅ **Chat Page**: Now uses Gemini AI instead of hardcoded responses
✅ **Firebase Authentication**: Email/password and Google sign-in
✅ **Error Handling**: Proper error messages for auth failures
✅ **User Context**: Global auth state management
✅ **Protected Routes**: Authentication state checking

## Notes

- The Apple sign-in button is disabled (requires Apple Developer account)
- All authentication is now handled by Firebase
- User sessions persist across browser refreshes
- The chat page now uses the same Gemini AI as the landing page
