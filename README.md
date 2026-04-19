# Eva Hospital

## System Context

This project is part of the EVA system. All EVA applications are connected together as one ecosystem.

Related Projects:

- [Eva Client](PUT_LINK_HERE)
- [Eva Doctor](PUT_LINK_HERE)
- [Eva Store](PUT_LINK_HERE)

## Overview

Eva Hospital is a dedicated application for hospital administrators and staff, completing the Eva healthcare ecosystem alongside Eva Client and Eva Doctor. This app provides the tools necessary to manage hospital operations, including doctor and patient management, service offerings, and appointment scheduling.

## Demo

(Add your demo video here)
[Watch Demo](PUT_YOUR_VIDEO_LINK_HERE)

## Features

- **Hospital Staff Authentication:** Secure login for authorized hospital personnel.
- **Appointment Management:** Oversee and manage all patient bookings and appointments for the hospital.
- **Doctor Management:** Add, edit, and manage the profiles of doctors associated with the hospital.
- **Service Management:** Control the medical services offered by the hospital, including descriptions and pricing.
- **Patient Records:** Access and manage the medical records of patients treated at the hospital.
- **Hospital Profile:** Update and maintain the hospital's information, such as address, contact details, and facilities.
- **Review Management:** Monitor and respond to patient reviews for the hospital and its doctors.
- **Community Engagement:** Publish articles, announcements, and other content to the community.
- **Notifications:** Receive important alerts related to bookings, patient inquiries, and system updates.
- Supports both English and Arabic.

## Tech Stack

- **Framework:** Flutter
- **State Management:** Flutter Riverpod
- **Routing:** Auto Route
- **API Client:** Dio

## Architecture

The project maintains the same feature-driven architecture as the other applications in the Eva ecosystem. This consistency simplifies development and ensures a scalable and maintainable codebase. Features are encapsulated in their own modules within the `features` directory, and a `core` directory provides shared functionalities. State management is handled by Riverpod.

## Folder Structure

```
lib/
├── app/
│   ├── core/
│   └── features/
│       ├── auth/
│       ├── bookings/
│       ├── community/
│       ├── doctors/
│       ├── edit_services/
│       ├── home_screen/
│       ├── intro/
│       ├── main_screen/
│       ├── my_information/
│       ├── notification/
│       ├── patient_medical_record/
│       ├── reviews/
│       └── setting/
├── generated/
├── router/
├── eva_app.dart
└── main.dart
```

## How It Works

Hospital staff can log in to the application to access the main dashboard, which provides an overview of the hospital's activities. From there, they can manage doctor schedules, approve or modify appointments, and update the services offered. The app also allows for the management of patient records and provides a platform for engaging with the patient community.

## Dependencies

- `flutter_riverpod`: For state management.
- `auto_route`: For navigation and routing.
- `dio`: For making HTTP requests to the API.
- `table_calendar`: For managing schedules and appointments.
- `image_picker`: For uploading images for hospital and doctor profiles.

## Notes

- This application is a crucial component of the Eva healthcare platform, providing essential tools for hospital administration.
- The consistent architecture across the client, doctor, and hospital apps is a significant advantage for the development team.
- The feature set is well-thought-out, covering the primary needs of a hospital in a digital healthcare environment.

Routes are defined in `lib/router/auto_router.dart` with `@AutoRoute()` annotations. The router supports RTL transitions (see `rightToLeftTransition`).

## Feature Structure

Features follow this structure:

```
lib/app/features/{feature_name}/
  presentation/
    screens/
      {screen_name}/
        {screen_name}_screen.dart
        widgets/  # Screen-specific widgets
        controllers/  # Riverpod controllers
```

Shared components live in `lib/app/core/widgets/`.

## RTL Support

The app supports Arabic (RTL) and English (LTR). Language preference is stored in `SharedPrefs` and accessed via `LangPrefs`. Font family switches between `Almarai` (Arabic) and English font based on locale.

## Build & Development

**Before committing**: Ensure all generated files are up-to-date:

1. `dart run build_runner build --delete-conflicting-outputs`
2. `dart run slang`
3. `dart run generate_styles.dart` (if style changes)

**Key files**:

- `lib/main.dart` - App initialization with `boot()` function
- `lib/eva_app.dart` - MaterialApp.router setup
- `lib/app/core/data/pref.dart` - SharedPreferences wrapper
- `lib/app/core/extensions/context_extensions.dart` - Navigation and UI extensions

## UI Converter Guidelines

When converting UI designs (e.g., from Figma) to Flutter code, use the following default image URL for placeholder images:

**Default Image URL**: `https://media.istockphoto.com/id/1352185969/photo/shot-of-a-young-woman-cheering-while-using-a-laptop-to-study-at-home.webp?s=612x612&w=is&k=20&c=yCI6qUI9Q4162uRowbhKKX1iqIpuAtxns8NhKYVrCpw=`

**Usage Example**:

```dart
// Use this URL as default for NetworkImage placeholders
NetworkImage("https://media.istockphoto.com/id/1352185969/photo/shot-of-a-young-woman-cheering-while-using-a-laptop-to-study-at-home.webp?s=612x612&w=is&k=20&c=yCI6qUI9Q4162uRowbhKKX1iqIpuAtxns8NhKYVrCpw=")

// Or use CustomCardImageView with the default URL
CustomCardImageView(
  height: 50,
  width: 50,
  imageUrl: 'https://media.istockphoto.com/id/1352185969/photo/shot-of-a-young-woman-cheering-while-using-a-laptop-to-study-at-home.webp?s=612x612&w=is&k=20&c=yCI6qUI9Q4162uRowbhKKX1iqIpuAtxns8NhKYVrCpw=',
)
```

**Note**: Replace placeholder images with actual image URLs from your API or assets when implementing real data.

## Common Patterns

- **Error handling**: Use `GeneralState` model with `success()`, `loading()`, `error()` states
- **Widgets**: Reusable widgets in `core/widgets/` (buttons, app bars, images)
- **Extensions**: Context extensions for navigation, styling, dialogs, bottom sheets
- **Constants**: App-wide constants in `lib/app/core/constants/`
