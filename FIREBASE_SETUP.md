# Firebase Authentication Setup

This project uses Firebase for Google authentication. Follow these steps to set up Firebase in your project:

## Step 1: Create a Firebase Project

1. Go to the [Firebase Console](https://console.firebase.google.com/)
2. Click "Add project"
3. Enter a project name and follow the setup wizard

## Step 2: Register Your App

1. On the Firebase project dashboard, click the web icon (</>) to add a web app
2. Register your app with a nickname
3. No need to set up Firebase Hosting now (you can do it later if needed)
4. Copy the Firebase configuration values that will be shown on screen

## Step 3: Configure Authentication

1. In the Firebase console, go to "Authentication" from the left sidebar
2. Click "Get started"
3. Select "Google" as a sign-in provider
4. Enable Google authentication and configure it
5. Save your changes

## Step 4: Set Up Environment Variables

1. Copy the `.env.local.example` file and rename it to `.env.local`
2. Fill in the Firebase configuration values:
   ```
   NEXT_PUBLIC_FIREBASE_API_KEY=your_firebase_api_key
   NEXT_PUBLIC_FIREBASE_AUTH_DOMAIN=your_project_id.firebaseapp.com
   NEXT_PUBLIC_FIREBASE_PROJECT_ID=your_project_id
   NEXT_PUBLIC_FIREBASE_STORAGE_BUCKET=your_project_id.appspot.com
   NEXT_PUBLIC_FIREBASE_MESSAGING_SENDER_ID=your_messaging_sender_id
   NEXT_PUBLIC_FIREBASE_APP_ID=your_app_id
   NEXT_PUBLIC_FIREBASE_MEASUREMENT_ID=your_measurement_id
   ```

## Step 5: Run the Application

After setting up the environment variables, start the application:

```bash
npm run dev
```

Your application should now use Google authentication with Firebase instead of Web3Auth! 