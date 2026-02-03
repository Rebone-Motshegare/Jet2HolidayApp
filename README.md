
Jet2Holiday App Logo
![514872703-bbcd7089-a742-4a82-b6d3-584446572a79](https://github.com/user-attachments/assets/56e80fff-b9e1-4423-8e32-e6aa3dc8fc54)


Publish to google play

<img width="1342" height="597" alt="511663092-c7759a45-bb3b-4769-96d8-d6dc2d0d0342" src="https://github.com/user-attachments/assets/d8dda1d4-7e5d-4fce-9f9a-f70eb451a478" />



##  Table of Contents

- [Features](#features)
- [Getting Started](#getting-started)
- [How to Use](#how-to-use)
- [Technology Stack](#technology-stack)
- [Project Structure](#project-structure)
- [Setup Instructions](#setup-instructions)
- [Testing](#testing)
- [Troubleshooting](#troubleshooting)

##  Features

###  Authentication & Security
- **Multiple Sign-In Options**: Email/Password and Google Sign-In (SSO)
- **Biometric Authentication**: Secure app access using fingerprint or face recognition
- **Email Verification**: OTP-style verification for new accounts
- **Password Reset**: Secure password reset via email links
- **Encrypted Storage**: User credentials stored securely with Android's Security Crypto

###  Holiday Package Management
- **Browse Packages**: View dynamic list of holiday packages from live backend API
- **Detailed Views**: Swipeable image galleries and comprehensive package information
- **Search & Filter**: Easy navigation through available packages
- **Real-time Data**: Package information synced with backend services

###  Booking System
- **Interactive Booking**: Select travel dates and number of guests
- **Price Calculation**: Automatic total price calculation
- **Real-time Updates**: Booking status updates (Pending, Confirmed, Rejected)
- **Booking History**: Complete history of all your bookings
- **Cancel Bookings**: Ability to cancel pending or confirmed bookings

### Smart Notifications
- **Push Notifications**: Instant alerts for booking confirmations/rejections
- **Notification Settings**: Manage notification preferences
- **Deep Integration**: Notifications open relevant app sections

### Accessibility & Localization
- **Multi-Language Support**: English and isiZulu (more languages can be added)
- **Auto-Detection**: Adapts to device language settings
- **Material Design 3**: Modern, accessible UI components
- **Offline Access**: View cached bookings without internet connection

###  Admin Features
- **Admin Dashboard**: Real-time view of all user bookings
- **Booking Management**: Approve or reject user bookings
- **Analytics**: Visual charts showing booking statistics
- **Role-Based Access**: Secure admin portal with proper authentication

##  Getting Started

### Prerequisites
- Android Studio Arctic Fox or later
- Android SDK 24 or higher
- Firebase account
- Google Cloud Console access (for Google Sign-In)

### Quick Setup

1. **Clone the Repository**
   ```bash
   git clone [your-repository-url]
   cd HolidayBooking
   ```

2. **Open in Android Studio**
   - Launch Android Studio
   - Select "Open an existing Android Studio project"
   - Navigate to the project folder and open

3. **Sync Dependencies**
   - Let Android Studio download and sync all Gradle dependencies
   - This may take a few minutes on first run

4. **Run the App**
   - Connect an Android device or start an emulator (API 24+)
   - Click the "Run" button or press `Shift + F10`

##  How to Use

### For Regular Users

#### 1. Getting Started
- **Register**: Create a new account with email and password
- **Verify Email**: Check your email for verification link
- **Alternative**: Use Google Sign-In for quick access
- **Biometric Setup**: Enable fingerprint/face unlock for convenience

#### 2. Browsing Packages
- **Home Screen**: View featured holiday packages
- **Package Details**: Tap any package to see full details
- **Image Gallery**: Swipe through package photos
- **Package Info**: Check prices, descriptions, and availability

#### 3. Making Bookings
- **Book Now**: Tap "Book" on any package
- **Select Dates**: Choose your travel dates
- **Guest Count**: Specify number of travelers
- **Review**: Check total price and details
- **Confirm**: Submit your booking request

#### 4. Managing Bookings
- **Bookings Tab**: View all your bookings
- **Status Tracking**: Monitor booking status changes
- **Booking History**: Access past booking records
- **Cancel**: Cancel unwanted bookings

#### 5. Profile Management
- **Profile Tab**: View account information
- **Settings**: Manage notification preferences
- **Language**: Switch between supported languages
- **Logout**: Securely sign out of the app

### For Administrators

#### 1. Admin Access
- **Admin Rights**: Contact system admin for role assignment
- **Admin Tab**: Access admin dashboard after login
- **Real-time Data**: View live booking information

#### 2. Booking Management
- **View All Bookings**: See bookings from all users
- **Status Updates**: Approve or reject booking requests
- **User Communication**: System sends automatic notifications
- **Analytics**: Monitor booking trends and statistics

##  Technology Stack

### Frontend (Android App)
- **Language**: Kotlin
- **UI Framework**: Jetpack Compose
- **Design System**: Material Design 3
- **Architecture**: MVVM (Model-View-ViewModel)
- **Navigation**: Jetpack Navigation Compose
- **Local Database**: Room Persistence Library
- **Image Loading**: Coil
- **Networking**: Ktor Client

### Backend Services
- **Authentication**: Firebase Authentication
- **Database**: Cloud Firestore
- **Push Notifications**: Firebase Cloud Messaging (FCM)
- **API Server**: Next.js (Vercel hosting)
- **Security**: Firebase Admin SDK

### Security Features
- **Biometric Authentication**: AndroidX Biometric
- **Encrypted Storage**: Security Crypto Library
- **Google SSO**: Google Sign-In SDK
- **Secure Communication**: HTTPS/TLS

##  Project Structure

```
app/
├── src/main/java/com/vcwaterfall/holidaybooking/
│   ├── auth/                    # Authentication screens
│   │   ├── LoginScreen.kt
│   │   ├── RegisterScreen.kt
│   │   ├── BiometricLockScreen.kt
│   │   └── PasswordResetScreen.kt
│   ├── main/                    # Main app screens
│   │   ├── dashboard/           # Package browsing
│   │   ├── bookings/           # Booking management
│   │   ├── admin/              # Admin features
│   │   └── profile/            # User profile
│   ├── navigation/             # Navigation logic
│   ├── util/                   # Helper utilities
│   │   ├── BiometricHelper.kt
│   │   ├── GoogleSignInHelper.kt
│   │   └── NotificationSettingsHelper.kt
│   └── ui/theme/              # UI theming
└── src/test/                  # Unit tests
```

##  Setup Instructions

### Firebase Configuration

1. **Create Firebase Project**
   - Go to [Firebase Console](https://console.firebase.google.com/)
   - Create a new project
   - Add Android app with package name: `com.vcwaterfall.holidaybooking`

2. **Download Configuration**
   - Download `google-services.json`
   - Place in `app/` directory

3. **Enable Services**
   - **Authentication**: Enable Email/Password and Google providers
   - **Firestore**: Create database with appropriate security rules
   - **Cloud Messaging**: Enable for push notifications

### Google Sign-In Setup

1. **Google Cloud Console**
   - Create OAuth 2.0 credentials
   - Add your app's SHA-1 fingerprint
   - Configure consent screen

2. **Add Client ID**
   - Add your OAuth client ID to `strings.xml`:
   ```xml
   <string name="google_client_id">YOUR_CLIENT_ID_HERE</string>
   ```

### Biometric Authentication

The app automatically detects biometric capabilities:
- Works with fingerprint sensors
- Supports face recognition
- Falls back gracefully if unavailable

##  Testing

### Running Unit Tests

```bash
# Run all tests
./gradlew test

# Run specific test class
./gradlew test --tests ValidationUtilsTest

# Run tests with coverage
./gradlew testDebugUnitTest
```

### Test Coverage
- Data model validation
- Authentication helpers
- Utility functions
- Business logic components

### Manual Testing Checklist
- [x] User registration and verification
- [x] Login with email/password
- [x] Google Sign-In flow
- [x] Biometric authentication
- [x] Package browsing
- [x] Booking creation
- [x] Notification handling
- [x] Admin functionalities

## 🔧 Troubleshooting

### Common Issues

#### Google Sign-In Error (Code 10)
**Problem**: `ApiException: 10` during Google Sign-In
**Solution**:
1. Verify SHA-1 fingerprint is added to Firebase
2. Check `google-services.json` is in correct location
3. Ensure Google Sign-In is enabled in Firebase Console
4. Verify OAuth client ID in `strings.xml`

#### Biometric Authentication Not Working
**Problem**: Biometric prompt not appearing
**Solution**:
1. Check device has biometric sensors
2. Ensure biometric is enrolled in device settings
3. Verify app has biometric permission
4. Test on different devices/emulators

#### Build Errors
**Problem**: Gradle sync failures
**Solution**:
1. Clean and rebuild: `Build > Clean Project`
2. Check internet connection
3. Update Android Studio and SDK
4. Verify `local.properties` has correct SDK path

#### Notification Issues
**Problem**: Push notifications not received
**Solution**:
1. Check FCM setup in Firebase
2. Verify notification permissions granted
3. Test on physical device (emulator limitations)
4. Check Firebase Cloud Messaging configuration

### Debug Commands

```bash
# Check app logs
adb logcat | grep HolidayBooking

# Clear app data
adb shell pm clear com.vcwaterfall.holidaybooking

# Check network requests
adb shell setprop log.tag.OkHttp DEBUG
```

##  Performance Tips

- **Offline Mode**: Bookings are cached locally for offline viewing
- **Image Loading**: Coil handles efficient image caching
- **Network Optimization**: Ktor provides efficient HTTP communication
- **Memory Management**: Compose handles UI state efficiently

##  Version History

- **v1.2**: Added biometric authentication and Google Sign-In
- **v1.1**: Implemented push notifications and admin features  
- **v1.0**: Initial release with core booking functionality

## Support

For technical issues or questions:
1. Check this README for common solutions
2. Review Firebase Console for backend issues
3. Check Android Studio build logs
4. Test on different devices/Android versions

##  Contributing

1. Fork the repository
2. Create feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit changes (`git commit -m 'Add AmazingFeature'`)
4. Push to branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

---

**Happy Holidays!**  Enjoy building and using the Holiday Booking app!
