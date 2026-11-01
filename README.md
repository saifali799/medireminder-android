# MediReminder

## Group Information

**Group Name:** [H]

**Group Members:**

| No. | Student Name | Student ID |
|---|---|---|
| 1 | Muhammad Saif | B23F1000CS174 |
| 2 | Ali Tahir | B24S0757CS057 |
| 3 | Abdullah Sheraz | B24S0877CS052 |
| 4 | Salar-ul-Islam | B24S0127CS018 |

## Project Description

MediReminder is an Android mobile application designed to help users organize and manage their medication schedules. It aims to reduce missed doses by allowing users to maintain medicine records, schedule medication reminders, and track their medication activities through a simple and user-friendly interface.

## Problem Statement

People who take medication regularly may forget scheduled doses or find it difficult to manage multiple medicines at different times. MediReminder aims to provide a simple solution for organizing medication schedules and reminding users when to take their medicines.

## Planned Features

### Must Have
- Add new medicines.
- View saved medicines.
- Edit and delete medicine records.
- Schedule medication reminders.
- Receive local notifications for scheduled doses.

### Should Have
- Mark doses as taken or skipped.
- Search medicines by name.
- View medication schedules.

### Could Have
- View medication dose history.
- Additional improvements to the user interface and user experience.

## Technology Stack

| Technology | Purpose |
|---|---|
| Flutter | Mobile application framework |
| Dart | Programming language |
| SQLite | Local database storage |
| Local Notifications | Medication reminders |

## Target Platform

**Android**

## Project Setup Instructions

### Prerequisites
- Flutter SDK
- Dart SDK (included with Flutter)
- Android Studio or Android SDK
- Visual Studio Code (recommended)

### Installation and Execution

1. Clone the repository:

   ```bash
   git clone https://github.com/saifali799/medireminder-android.git
   ```

2. Navigate to the project directory:

   ```bash
   cd medireminder-android
   ```

3. Install project dependencies:

   ```bash
   flutter pub get
   ```

4. Connect an Android device or start an emulator.

5. Run the application:

   ```bash
   flutter run
   ```

## Project Status

This repository contains the initial Flutter project setup for MediReminder. The application features and integrations are planned for implementation in subsequent assignments.





## Contributing
1. Fork the repository and clone your fork.
2. Create a branch: `git checkout -b feature/your-feature`
3. Commit your changes with a clear message.
4. Push the branch and open a pull request to `main`.
## Tested Environment

| Tool | Version |
|---|---|
| Flutter | 3.47.9 (stable) |
| Dart | 3.13.7 |
| OS | Ubuntu Linux |

Run `flutter doctor` to check that your setup matches before running the app.
## Development Roadmap

### Must Have
- [ ] Add new medicines
- [ ] View saved medicines
- [ ] Edit and delete medicine records
- [ ] Schedule medication reminders
- [ ] Local notifications for scheduled doses

### Should Have
- [ ] Mark doses as taken or skipped
- [ ] Search medicines by name
- [ ] View medication schedules

### Could Have
- [ ] View medication dose history
- [ ] UI and UX improvements
## Planned Screens

| Screen | Purpose |
|---|---|
| Medicine List | View, search, and delete saved medicines |
| Add / Edit Medicine | Enter name, dosage, and notes |
| Reminder Setup | Choose times and days for each medicine |
| Today's Schedule | See today's doses and mark them taken or skipped |
| Dose History | Review past taken and skipped doses |
## Proposed Database Schema

*Draft for the group to review. SQLite tables:*

**medicines**

| Column | Type | Notes |
|---|---|---|
| id | INTEGER | Primary key, auto-increment |
| name | TEXT | Required |
| dosage | TEXT | Required, e.g. "500 mg" |
| notes | TEXT | Optional |

**reminders**

| Column | Type | Notes |
|---|---|---|
| id | INTEGER | Primary key, auto-increment |
| medicine_id | INTEGER | Foreign key to medicines.id, delete cascades |
| time | TEXT | "HH:mm" |
| days_of_week | TEXT | e.g. "Mon,Wed,Fri" |
| is_active | INTEGER | 1 = on, 0 = off |

**dose_logs**

| Column | Type | Notes |
|---|---|---|
| id | INTEGER | Primary key, auto-increment |
| medicine_id | INTEGER | Foreign key to medicines.id |
| scheduled_at | TEXT | ISO 8601 date and time |
| status | TEXT | "taken" or "skipped" |
| logged_at | TEXT | ISO 8601 date and time |
## Git Conventions

- Create one branch per feature: `feature/medicine-list`, `fix/reminder-bug`.
- Do not push directly to `main`. Open a pull request and get a review.
- Write commit messages in the imperative: "Add medicine form", not "Added medicine form".
- Keep each commit to one change.
- Run `git pull upstream main` before starting new work.

- ## Folder Structure


medireminder-android/
├── lib/
│   ├── main.dart            # App entry point
│   ├── models/              # Data classes (Medicine, Reminder, DoseLog)
│   ├── database/            # SQLite helper and queries
│   ├── screens/             # UI screens (list, form, schedule, history)
│   ├── services/            # Notification scheduling logic
│   └── widgets/             # Reusable UI components
├── android/                 # Android platform files
├── test/                    # Unit and widget tests
└── pubspec.yaml             # Dependencies and project config

