# Photo Gallery Android App

A modern Android gallery app designed for Android 13+ that allows users to browse camera photos with time range filtering, select multiple photos, and share or import them to Google Photos.

## Features

### 🎯 Core Functionality
- **Time Range Filtering**: Select start and end dates to filter photos from camera folder
- **Photo Library Display**: Grid view of photos with modern card design
- **Multi-Selection**: Select multiple photos with visual feedback
- **Share Photos**: Share selected photos using Android's native sharing
- **Google Photos Import**: Import selected photos to Google Photos (simulated)

### 📱 Android 13+ Optimized
- **Granular Media Permissions**: Uses `READ_MEDIA_IMAGES` for Android 13+
- **Modern Material Design 3**: Clean, modern UI following Material Design guidelines
- **Responsive Layout**: Optimized for various screen sizes
- **Performance Optimized**: Efficient image loading with Glide

## Project Structure

```
app/
├── src/main/
│   ├── java/com/gallery/photoapp/
│   │   ├── MainActivity.kt              # Entry point with permission handling
│   │   ├── GalleryActivity.kt           # Main gallery with photo grid
│   │   ├── PhotoPreviewActivity.kt      # Full-screen photo preview
│   │   ├── model/
│   │   │   └── Photo.kt                 # Photo data model
│   │   ├── viewmodel/
│   │   │   └── GalleryViewModel.kt      # Gallery state management
│   │   └── adapter/
│   │       └── PhotoAdapter.kt          # RecyclerView adapter for photos
│   ├── res/
│   │   ├── layout/                      # XML layouts
│   │   ├── drawable/                    # Icons and backgrounds
│   │   ├── values/                      # Colors, strings, themes
│   │   └── xml/                         # Configuration files
│   └── AndroidManifest.xml             # App configuration
├── build.gradle.kts                    # App-level build configuration
└── proguard-rules.pro                  # ProGuard rules
```

## Key Components

### MainActivity
- Handles storage permissions for Android 13+
- Modern welcome screen with feature highlights
- Smooth transition to gallery

### GalleryActivity
- Loads photos from camera folder using MediaStore API
- Date range picker using Material Date Picker
- Grid layout with 3 columns
- Selection management with visual feedback
- Action buttons for share and import

### PhotoAdapter
- Efficient RecyclerView adapter with DiffUtil
- Glide integration for smooth image loading
- Selection state management
- Click and long-click handling

### GalleryViewModel
- MVVM architecture with LiveData
- Date range filtering logic
- Selection state management
- Loading state handling

## Permissions

The app requests the following permissions:

### Android 13+ (API 33+)
- `READ_MEDIA_IMAGES` - Access to image files
- `READ_MEDIA_VIDEO` - Access to video files (future use)

### Android 12 and below
- `READ_EXTERNAL_STORAGE` - Access to external storage

## Dependencies

### Core Android
- AndroidX Core KTX
- AppCompat
- Material Design Components
- ConstraintLayout
- Lifecycle (ViewModel, LiveData)
- Activity & Fragment KTX

### Image Loading
- Glide 4.16.0 - Efficient image loading and caching

### Google Services
- Google Play Services Auth
- Google API Client
- Google Photos Library API

## Build Requirements

- **Minimum SDK**: 33 (Android 13)
- **Target SDK**: 34 (Android 14)
- **Compile SDK**: 34
- **Kotlin**: 1.9.10
- **Gradle**: 8.2.0

## Installation

1. Open the project in Android Studio
2. Sync Gradle files
3. Build and run on Android 13+ device or emulator

## Usage

1. **Launch App**: Grant storage permissions when prompted
2. **Browse Photos**: View all camera photos in grid layout
3. **Filter by Date**: Tap "Select Range" to filter photos by date
4. **Select Photos**: Tap photos to select/deselect (checkbox appears)
5. **Share**: Use share button to share selected photos
6. **Import**: Use import button to upload to Google Photos

## Architecture

The app follows **MVVM (Model-View-ViewModel)** architecture:

- **Model**: `Photo` data class
- **View**: Activities and XML layouts
- **ViewModel**: `GalleryViewModel` for state management

## Features in Detail

### Time Range Filtering
- Material Date Range Picker
- Filters photos by `DATE_TAKEN` metadata
- Real-time filtering with smooth animations

### Photo Selection
- Visual feedback with overlay and checkbox
- Batch operations (Select All/Deselect All)
- Selection count display

### Sharing
- Native Android sharing intent
- Supports single and multiple photo sharing
- Proper URI permissions for external apps

### Google Photos Integration
- OAuth authentication flow
- Batch upload capability
- Progress indication and error handling

## Future Enhancements

- [ ] Video support
- [ ] Cloud storage integration (Dropbox, OneDrive)
- [ ] Photo editing capabilities
- [ ] Album organization
- [ ] Search functionality
- [ ] Backup scheduling

## License

This project is created for educational purposes.
