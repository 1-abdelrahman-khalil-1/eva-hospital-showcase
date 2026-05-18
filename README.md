# EVA Hospital

Hospital-operations mobile application in the EVA healthcare ecosystem.

## 1. Hero Section

EVA Hospital is built around hospital-side operations, with flows that support coordination, content management, and operational review:

- booking oversight and coordination
- doctor and service management
- medical record access from hospital workflows
- community/review and notification operations

## 2. Ecosystem Context

EVA Hospital covers the administrative layer of the EVA ecosystem. It supports the workflows that sit between patient demand and doctor execution.

## 3. Engineering Highlights

- Feature modules are grouped by operational domain, which keeps bookings, services, doctors, and reviews independent.
- Riverpod is used for fetch flows and mutation flows with a shared async-state pattern across screens.
- AutoRoute owns the hospital navigation structure and generated route outputs.
- Shared core code handles API helpers, preferences, widgets, and extensions so operational screens stay thin.
- Arabic/English support follows the same persisted locale and RTL/LTR-aware behavior used in the rest of EVA.

## 4. Screenshots / Demo Placeholder

- Product walkthrough: ADD_VIDEO_OR_GIF_LINK
- App screenshots: ADD_SCREENSHOT_LINKS

## 5. Tech Stack

- Flutter (Dart 3)
- flutter_riverpod
- auto_route + build_runner
- dio
- slang / slang_flutter
- shared_preferences

## 6. Architecture Overview

1. Startup boot flow restores preferences and locale settings before rendering the app shell.
2. The router layer centralizes navigation and generated route contracts for the full hospital flow.
3. Features keep data access and presentation concerns separated so each operational domain stays contained.
4. API and error handling logic is consolidated in shared core helpers rather than duplicated in feature code.
5. Shared widget and extension layers keep dialog, navigation, and sizing behavior consistent across modules.

## 7. Simplified Folder Structure

```text
lib/
  app/
    core/
    features/
      auth/
      bookings/
      community/
      doctors/
      edit_services/
      home_screen/
      intro/
      main_screen/
      my_information/
      notification/
      patient_medical_record/
      reviews/
      setting/
  generated/
  router/
  eva_app.dart
  main.dart
```

## 8. System Architecture Diagram (ASCII)

```text
Presentation Layer
      |
      v
Riverpod Providers
      |
      v
Feature Repositories
      |
      v
Core API Helpers
      |
      v
EVA Backend
```

## 9. My Responsibilities / Scope

- Delivered hospital-facing feature modules and their supporting flows.
- Structured provider logic for reads, mutations, and refresh cycles.
- Kept API integrations aligned with shared error handling and request setup.
- Maintained route structure and generated navigation outputs.
- Reused shared patterns so operational screens follow the same implementation style.

## 10. Repository Notes

- This repository is maintained as a portfolio showcase.
- The README highlights implementation shape and hospital workflow scope, not setup steps.
