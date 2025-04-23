# BitSciSha Android App - Technical Documentation

## Architecture Overview
The BitSciSha Android app is built using the MVVM (Model-View-ViewModel) architecture pattern with Jetpack Compose for the UI. The app uses Firebase for authentication, database, and cloud functions.

### Key Components
- **UI Layer**: Jetpack Compose screens and components
- **ViewModel Layer**: AuthViewModel and AdminViewModel
- **Repository Layer**: AuthRepository and AdminRepository
- **Data Layer**: Firebase Authentication, Firestore, and Cloud Functions

## Project Structure
```
com.bitscisha.app/
├── BitSciShaApplication.kt
├── MainActivity.kt
├── data/
│   ├── auth/
│   │   ├── AuthExtensions.kt
│   │   ├── AuthRepository.kt
│   │   ├── AuthState.kt
│   │   └── AuthViewModel.kt
│   └── admin/
│       ├── AdminRepository.kt
│       ├── AdminState.kt
│       ├── AdminViewModel.kt
│       ├── NotificationData.kt
│       └── UserData.kt
├── di/
│   └── FirebaseModule.kt
└── ui/
    ├── components/
    │   ├── CosmicBackground.kt
    │   └── SocialLoginButton.kt
    ├── navigation/
    │   └── BitSciShaNavHost.kt
    ├── screens/
    │   ├── admin/
    │   │   ├── AdminDashboardScreen.kt
    │   │   └── NotificationsScreen.kt
    │   ├── auth/
    │   │   ├── LoginScreen.kt
    │   │   └── RegisterScreen.kt
    │   ├── main/
    │   │   ├── AboutScreen.kt
    │   │   ├── CommunityScreen.kt
    │   │   ├── MainScreen.kt
    │   │   ├── TopicsScreen.kt
    │   │   └── VideosScreen.kt
    │   └── splash/
    │       └── SplashScreen.kt
    └── theme/
        ├── Color.kt
        ├── Shape.kt
        ├── Theme.kt
        └── Type.kt
```

## Dependencies
- **Jetpack Compose**: UI toolkit
- **Hilt**: Dependency injection
- **Firebase Auth**: Authentication
- **Firebase Firestore**: Database
- **Firebase Functions**: Cloud functions
- **Kotlin Coroutines**: Asynchronous programming
- **Coil**: Image loading

## Authentication System
The authentication system supports:
- Email/password authentication
- Google Sign-In
- Facebook Sign-In
- Apple Sign-In

### Authentication Flow
1. User enters credentials or selects social login
2. AuthRepository handles the authentication request
3. AuthViewModel updates the UI state based on the result
4. On successful authentication, user is redirected to the main screen

## Admin System
The admin system provides:
- User management (view, reset password, change role, delete)
- Notification system for new user registrations

### Admin Flow
1. Admin user logs in
2. Admin icon appears in the top bar
3. Admin can access the admin dashboard
4. Admin can manage users and view notifications

## Firebase Integration
### Authentication
- Firebase Authentication is used for all authentication methods
- User profiles are stored in Firestore

### Database
- Firestore is used to store user data and notifications
- Security rules ensure only authorized access

### Cloud Functions
- Cloud Functions are used for admin operations like password reset and user deletion
- Cloud Functions also handle sending email notifications to the admin

## UI Components
### Theme
- Custom theme based on the BitSciSha website
- Dark theme with cosmic background
- Custom typography and color scheme

### Navigation
- Bottom navigation for main sections
- Stack navigation for authentication and admin screens

### Screens
- Splash screen with animations
- Authentication screens (login, register)
- Main content screens (videos, topics, about, community)
- Admin screens (dashboard, notifications)

## Testing
- Unit tests for repositories and view models
- UI tests for screens and components
- Integration tests for Firebase integration

## Deployment
- The app is built as an APK file
- Minimum Android version: 5.0 (API level 21)
- Target Android version: 13 (API level 33)

## Future Improvements
- Implement offline mode
- Add push notifications
- Enhance video playback features
- Add user profile customization
- Implement analytics
