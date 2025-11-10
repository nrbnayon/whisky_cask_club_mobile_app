# Whisky Cask Club Mobile App

A comprehensive React Native mobile application for whisky cask investment management, featuring real-time notifications, referral rewards, portfolio tracking, and seamless cask purchasing experience.

## 📱 Features

### Core Functionality
- **User Authentication**: Secure sign-up, sign-in, password reset with OTP verification
- **Cask Management**: Browse, search, and filter available whisky casks
- **Portfolio Tracking**: Monitor your cask investments and lifetime profit gains
- **Order Management**: Place orders, express interest, and track purchase history
- **Referral System**: Earn points through user referrals with reward tracking
- **Real-time Notifications**: Firebase Cloud Messaging integration for instant updates
- **Exclusive Offers**: Access special deals and promotional offers
- **Profile Management**: Edit profile, change password, and manage account settings
- **Dark Mode Support**: Automatic theme switching based on system preferences

### User Experience
- **Intuitive Navigation**: Tab-based navigation with bottom bar
- **Responsive Design**: Optimized for various screen sizes
- **Pull-to-Refresh**: Real-time data synchronization
- **Empty States**: User-friendly messages for empty data scenarios
- **Error Handling**: Comprehensive error management with user feedback
- **Activity Feed**: Track all your interactions and transactions

## 🏗️ Project Structure

```
Whisky Mobile APP Frontend/
├── app/                          # App screens and navigation
│   ├── (auth)/                  # Authentication screens
│   │   ├── sign-in.tsx
│   │   ├── sign-up.tsx
│   │   ├── forgot-password.tsx
│   │   ├── reset-password.tsx
│   │   └── verify-otp.tsx
│   ├── (main)/                  # Main app screens
│   │   ├── index.tsx            # Home/Dashboard
│   │   ├── portfolio.tsx        # Cask portfolio
│   │   ├── offers.tsx           # Special offers
│   │   ├── my-purchase.tsx      # Purchase history
│   │   ├── profile.tsx          # User profile
│   │   ├── referral.tsx         # Referral system
│   │   ├── cask/[id].tsx        # Cask details
│   │   ├── offer-details/[id].tsx
│   │   ├── purchase-details/[id].tsx
│   │   └── express-interest/[id].tsx
│   └── (screen)/                # Additional screens
│       ├── notifications.tsx
│       ├── privacy-policy.tsx
│       └── terms-conditions.tsx
├── components/                   # Reusable components
│   ├── ui/                      # Base UI components
│   │   ├── Button.tsx
│   │   ├── Input.tsx
│   │   ├── Card.tsx
│   │   ├── LoadingSpinner.tsx
│   │   └── ThemeContext.tsx
│   └── shared/                  # Feature-specific components
│       ├── CaskCard.tsx
│       ├── OfferCard.tsx
│       ├── StatsCard.tsx
│       ├── ActivityItem.tsx
│       └── NotificationCard.tsx
├── services/                     # API services
│   ├── authService.ts
│   ├── caskService.ts
│   ├── offerService.ts
│   ├── purchaseService.ts
│   ├── referralService.ts
│   ├── notificationService.ts
│   └── firebaseNotificationService.ts
├── store/                        # State management
│   └── useAppStore.ts           # Zustand store
├── hooks/                        # Custom React hooks
│   ├── useAuth.ts
│   ├── useApi.ts
│   └── useFirebaseNotifications.ts
├── utils/                        # Utility functions
│   ├── apiClient.ts
│   ├── formatters.ts
│   ├── validationSchemas.ts
│   ├── errorHandler.ts
│   └── toast.ts
└── config/                       # Configuration files
    └── firebase.ts              # Firebase setup
```

## 🚀 Getting Started

### Prerequisites

- Node.js (v18 or higher)
- npm or yarn
- React Native development environment
- Expo CLI
- Android Studio (for Android development)
- Xcode (for iOS development, macOS only)

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/nrbnayon/Whisky-Cask-Club-APP.git
   cd "Whisky Mobile APP Frontend"
   ```

2. **Install dependencies**
   ```bash
   yarn install
   # or
   npm install
   ```

3. **Configure environment variables**
   ```bash
   cp .env.example .env
   ```
   
   Update `.env` with your configuration:
   ```env
   API_BASE_URL=your_api_url
   FIREBASE_API_KEY=your_firebase_key
   FIREBASE_AUTH_DOMAIN=your_auth_domain
   FIREBASE_PROJECT_ID=your_project_id
   FIREBASE_STORAGE_BUCKET=your_storage_bucket
   FIREBASE_MESSAGING_SENDER_ID=your_sender_id
   FIREBASE_APP_ID=your_app_id
   ```

4. **Configure Firebase**
   - Place `google-services.json` in the root directory (Android)
   - Place `GoogleService-Info.plist` in the root directory (iOS)
   - Follow the guides in `FIREBASE_NOTIFICATIONS_SETUP.md`

### Running the App

#### Development Mode

```bash
# Start the Expo development server
yarn start

# Run on Android
yarn android

# Run on iOS
yarn ios

# Run on web
yarn web
```

#### Production Build

```bash
# Build for Android
eas build --platform android

# Build for iOS
eas build --platform ios

# Build for both platforms
eas build --platform all
```

## 🔧 Technology Stack

### Core Technologies
- **React Native** - Cross-platform mobile framework
- **Expo** - Development and build platform
- **TypeScript** - Type-safe JavaScript
- **Expo Router** - File-based routing system

### UI & Styling
- **NativeWind** - Tailwind CSS for React Native
- **Lucide React Native** - Icon library
- **React Native Reanimated** - Animations

### State Management
- **Zustand** - Lightweight state management
- **React Context** - Theme management

### Backend Integration
- **Axios** - HTTP client
- **Firebase Cloud Messaging** - Push notifications
- **AsyncStorage** - Local data persistence

### Development Tools
- **ESLint** - Code linting
- **Prettier** - Code formatting
- **TypeScript** - Static type checking

## 📂 Key Configuration Files

- `app.json` - Expo configuration
- `eas.json` - EAS Build configuration
- `babel.config.js` - Babel configuration
- `tailwind.config.js` - Tailwind CSS configuration
- `metro.config.js` - Metro bundler configuration
- `tsconfig.json` - TypeScript configuration

## 🔔 Firebase Notifications

The app includes comprehensive Firebase Cloud Messaging integration:

- **Real-time notifications** for order updates
- **Background notification handling**
- **Notification permission management**
- **Custom notification sounds and icons**

Refer to the following documentation:
- `FIREBASE_NOTIFICATIONS_SETUP.md` - Setup guide
- `FIREBASE_NOTIFICATIONS_API.md` - API documentation
- `POSTMAN_FIREBASE_NOTIFICATIONS.md` - Testing guide

## 🎨 Theming

The app supports both light and dark modes with automatic system preference detection:

```typescript
import { useColorScheme } from '@/hooks/useColorScheme';

const colorScheme = useColorScheme();
// Returns 'light' or 'dark' based on system preference
```

## 📱 Key Features Implementation

### Authentication Flow
- Email/password authentication
- OTP verification for password reset
- Persistent login with secure token storage
- Automatic token refresh

### Cask Management
- Browse available casks with filtering
- Detailed cask information and specifications
- Express interest in premium casks
- Track cask performance and valuation

### Referral System
- Unique referral codes for each user
- Point-based reward system
- Track referral history and earnings
- Share referral links via social media

### Order Tracking
- Real-time order status updates
- Purchase history with detailed invoices
- Lifetime profit calculations
- Portfolio performance metrics

## 🧪 Testing

```bash
# Run tests
yarn test

# Run tests with coverage
yarn test:coverage

# Run linter
yarn lint

# Fix linting issues
yarn lint:fix
```

## 📦 Building for Production

### Android
1. Update version in `app.json`
2. Run `eas build --platform android`
3. Submit to Google Play Store: `eas submit --platform android`

### iOS
1. Update version in `app.json`
2. Run `eas build --platform ios`
3. Submit to App Store: `eas submit --platform ios`

## 🔐 Security

- Secure token storage using AsyncStorage
- API request encryption
- Input validation and sanitization
- Protected routes for authenticated users
- Secure password reset flow

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📄 License

This project is proprietary and confidential.

## 👥 Support

For support, please contact the development team or refer to the internal documentation.

## 🔄 Version History

- **v1.0.0** - Initial release
  - Core authentication features
  - Cask browsing and management
  - Portfolio tracking
  - Referral system
  - Push notifications

## 📞 Contact

For any inquiries or support, please reach out to the project maintainers.

---

**Built with ❤️ for Whisky Cask Club**
