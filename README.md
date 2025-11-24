# Milk Filter - Artistic Image Processing for Android

A sophisticated Android native application for artistic image processing with glassmorphism design, smooth animations, and professional UI/UX.

## 🎨 Features

- **📸 Image Upload** - Pick images from gallery or capture with camera
- **🎨 Artistic Filters** - Apply Milk 1 (purple/pink) or Milk 2 (red/brown) filters
- **✨ Pointillism Mode** - Toggle pointillism effect on/off
- **📊 Compression Control** - Adjust compression from 0-100%
- **🔄 Before/After Comparison** - Interactive slider to compare original vs filtered
- **💾 Download & Share** - Save or share processed images
- **🎯 Gallery History** - View all processed images

## 🛠️ Technology Stack

- **Framework**: React Native with Expo SDK 54
- **Navigation**: React Navigation 7
- **Animations**: React Native Reanimated 3
- **Typography**: Poppins & Roboto fonts via Expo Google Fonts
- **UI Effects**: 
  - Glassmorphism design with blur effects
  - Smooth Spring animations
  - Haptic feedback
- **Image Processing**: Expo Image Picker
- **Storage**: AsyncStorage for local data

## 📱 Design System

### Color Palette
- **Primary**: #890028 (Wine Red)
- **Hover**: #8b0a2f
- **Background**: Dark theme with glassmorphism effects
- **Glass Effects**: Transparent overlays with blur

### Typography
- **Headlines**: Poppins Bold, SemiBold
- **Body**: Poppins Regular, Medium
- **Captions**: Roboto Regular

### Spacing
- **xs**: 4px
- **sm**: 8px
- **md**: 16px
- **lg**: 24px
- **xl**: 32px

## 🚀 Getting Started

### Prerequisites
- Node.js 18+
- npm or yarn
- Expo CLI

### Installation

```bash
# Clone repository
git clone https://github.com/[username]/milk-filter.git
cd milk-filter

# Install dependencies
npm install

# Install Expo CLI globally
npm install -g expo-cli

# Start development server
npm run dev
```

### Running on Android

#### Option 1: Expo Go (Development)
```bash
npm run dev
# Scan QR code with Expo Go app on your Android phone
```

#### Option 2: EAS Build (Production APK)
```bash
# Install EAS CLI
npm install -g eas-cli

# Build APK
eas build --platform android --local

# Download APK when ready
```

## 📁 Project Structure

```
milk-filter/
├── screens/
│   ├── EditorScreen.tsx      # Main editor with filters
│   └── GalleryScreen.tsx     # Image gallery history
├── components/
│   ├── GlassCard.tsx         # Glass effect card component
│   ├── GlassButton.tsx       # Glass effect button
│   ├── GlassInput.tsx        # Glass effect input field
│   ├── ImageUploadCard.tsx   # Image upload interface
│   ├── ThemedText.tsx        # Themed text component
│   └── ThemedView.tsx        # Themed view component
├── navigation/
│   ├── MainTabNavigator.tsx  # Bottom tab navigation
│   ├── EditorStackNavigator.tsx
│   └── GalleryStackNavigator.tsx
├── hooks/
│   ├── useImageFilter.ts     # Filter state management
│   ├── useTheme.ts           # Theme hook
│   └── useScreenInsets.ts    # Safe area insets
├── constants/
│   └── theme.ts              # Color, typography, spacing
├── assets/
│   └── images/
│       ├── icon.png          # App icon
│       ├── splash-icon.png   # Splash screen
│       └── avatars/
├── app.json                  # Expo configuration
├── App.tsx                   # Root component with fonts
└── README.md
```

## 🎯 Usage

### 1. Upload an Image
- Tap the upload card to select an image from gallery or camera
- Image will be displayed for processing

### 2. Configure Filters
- Select **Milk 1** (purple gradient) or **Milk 2** (red gradient)
- Toggle **Pointillism** for artistic effect
- Adjust **Compression** slider (0-100%)

### 3. Apply Filter
- Tap "Aplicar Filtro" button
- Processing animation shows while filter is applied
- Filtered result appears below

### 4. Compare Images
- Use the interactive slider in comparison view
- Drag to see before/after side-by-side

### 5. Save & Share
- **Download**: Save filtered image to device
- **Share**: Send via messaging, email, social media
- **New Upload**: Start fresh with another image

## 🎨 Design Highlights

### Glassmorphism
- Frosted glass effect on all cards and buttons
- Blur backdrop with transparency
- Smooth transitions and spring animations

### Responsive Layout
- Optimized for portrait orientation
- Safe area awareness for notches and system ui
- Touch-friendly button sizes (48x48px minimum)

### Animations
- Page transitions: 350ms ease-out
- Component interactions: Spring animations
- Scale effects on press: 0.95x
- Haptic feedback on interactions

## 🔧 Configuration

### Android Configuration (app.json)
```json
{
  "android": {
    "package": "com.milkfilter.mobile",
    "minSdkVersion": 31,
    "targetSdkVersion": 35,
    "compileSdkVersion": 35
  }
}
```

### Environment Variables
None required for MVP version

## 📝 Development

### Scripts
```bash
npm run dev          # Start Expo dev server
npm run build        # Build static bundle
npm run lint         # Run ESLint
```

### Code Conventions
- TypeScript for type safety
- Functional components with hooks
- Reusable component patterns
- Theme tokens for consistent styling

## 🐛 Troubleshooting

### App not loading
- Clear Metro cache: `npm run dev -- --clear`
- Restart dev server: `ctrl+c` then `npm run dev`

### Images not displaying
- Ensure image permissions are granted
- Check image URI is valid
- Verify image format (JPG, PNG)

### Filter not applying
- Check processing time (~1.5s)
- Ensure image is selected
- Look at console logs for errors

## 📦 Building for Release

### Sign APK with Keystore
```bash
# Generate keystore (one time)
keytool -genkey -v -keystore ~/my-release-key.keystore -keyalg RSA -keysize 2048 -validity 10000 -alias my-key-alias

# Build with signing
eas build --platform android --local
```

### Upload to Google Play Store
1. Create Google Play Developer account
2. Create app listing
3. Upload signed APK
4. Configure store listing details
5. Submit for review

## 🤝 Contributing

1. Fork repository
2. Create feature branch: `git checkout -b feature/amazing-feature`
3. Commit changes: `git commit -m 'Add amazing feature'`
4. Push to branch: `git push origin feature/amazing-feature`
5. Open Pull Request

## 📄 License

This project is licensed under the MIT License - see LICENSE file for details.

## 🙏 Acknowledgments

- React Native community
- Expo team for amazing tools
- Design inspiration from modern mobile apps

## 📞 Support

For issues and questions:
- 📧 Email: support@milkfilter.dev
- 🐛 GitHub Issues: [Report Bug](https://github.com/[username]/milk-filter/issues)
- 💬 Discussions: [Join Community](https://github.com/[username]/milk-filter/discussions)

---

**Made with ❤️ using React Native & Expo**
