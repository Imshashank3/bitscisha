# BitSciSha Android App - Setup Instructions

## Firebase Setup

To fully enable the authentication and admin features, you'll need to set up Firebase for your app:

1. **Create a Firebase Project**:
   - Go to the [Firebase Console](https://console.firebase.google.com/)
   - Click "Add project" and follow the setup wizard
   - Enable Google Analytics if desired

2. **Register Your App**:
   - In the Firebase console, click "Add app" and select Android
   - Enter package name: `com.bitscisha.app`
   - Download the `google-services.json` file and place it in the app directory

3. **Enable Authentication Methods**:
   - In the Firebase console, go to Authentication > Sign-in method
   - Enable Email/Password, Google, Facebook, and Apple authentication
   - Configure OAuth redirects for social providers

4. **Set Up Firestore Database**:
   - In the Firebase console, go to Firestore Database
   - Create a database in production mode
   - Set up the following collections:
     - `users`: To store user profiles
     - `admin_notifications`: To store notifications for admin

5. **Deploy Cloud Functions**:
   - Set up Firebase CLI on your development machine
   - Deploy the provided cloud functions for admin features

## Social Login Configuration

### Google Sign-In
1. Configure your OAuth consent screen in Google Cloud Console
2. Create OAuth client ID for Android
3. Add the client ID to your Firebase project

### Facebook Sign-In
1. Create a Facebook Developer account
2. Register your app on Facebook Developer portal
3. Configure Facebook Login product
4. Add your Facebook App ID to the app's strings.xml

### Apple Sign-In
1. Create an Apple Developer account
2. Register your app in Apple Developer portal
3. Configure Sign in with Apple capability
4. Add the necessary configuration to your Firebase project

## Building the App

1. **Open the project in Android Studio**:
   - Import the project from the provided source code
   - Ensure you have the latest Android SDK and build tools

2. **Install Dependencies**:
   - Sync the project with Gradle files
   - Ensure all dependencies are properly resolved

3. **Configure Build Variables**:
   - Update the `applicationId` in app/build.gradle if needed
   - Set the version code and version name

4. **Build the App**:
   - Select Build > Build Bundle(s) / APK(s) > Build APK
   - The APK will be generated in app/build/outputs/apk/

## Testing the App

1. **Install on a Device or Emulator**:
   - Transfer the APK to your device or use Android Studio to install on an emulator
   - Enable installation from unknown sources if installing directly on a device

2. **Test Authentication**:
   - Create a new account
   - Sign in with existing account
   - Test social login options

3. **Test Admin Features**:
   - Sign in with an admin account
   - Access the admin dashboard
   - Test user management features

## Customization

1. **Branding**:
   - Update app icons in res/mipmap directories
   - Modify colors in ui/theme/Color.kt
   - Update strings in res/values/strings.xml

2. **Content**:
   - Update video content in VideosScreen.kt
   - Update topic content in TopicsScreen.kt
   - Update about content in AboutScreen.kt

3. **Shop Integration**:
   - Update the Shopify store URL in MainScreen.kt

## Troubleshooting

- **Build Issues**: Ensure you have the correct SDK version and build tools
- **Firebase Connection Issues**: Verify your google-services.json file is correctly placed
- **Authentication Issues**: Check Firebase Authentication configuration
- **Admin Features Not Working**: Verify Firestore security rules and collections

## Contact

For any technical issues or questions, please contact the development team at bitscisha.com.
