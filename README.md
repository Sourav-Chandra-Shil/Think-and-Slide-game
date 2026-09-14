# 🧩 Think and Slide

> **A modern Flutter-based sliding puzzle game combining logical gameplay, interactive UI, persistent progress, and cloud-powered player features.**

**Think and Slide** is a mobile sliding-puzzle game developed with **Flutter and Dart**, designed to modernize the classic sliding puzzle with an engaging visual experience and a complete set of gameplay and progression features.

The application combines a solvability-preserving puzzle engine with **Firebase Authentication, Cloud Firestore, local persistence, daily streaks, global rankings, multiple themes, audio controls, and vibration feedback**.

---

## ✨ Features

* 🧩 **Image-Based Sliding Puzzles**
* 🎯 **Multiple Difficulty Modes**

  * Easy
  * Medium
  * Hard
  * Free To Play
* 📈 **Level Progression**
* ⏱️ **Timer & Move Counter**
* 🏆 **Score Calculation**
* 🔐 **Google Sign-In**
* 👤 **Guest / Local Play**
* ☁️ **Cloud Progress Synchronization**
* 🔥 **Daily Streak System**
* 🌎 **Global Leaderboard**
* 🎨 **Multiple Visual Themes**
* 🎵 **Background Music & Audio Controls**
* 📳 **Vibration Feedback**
* 💾 **Local Progress Persistence**
* 📱 **Responsive Mobile UI**

The project currently provides 10 configured levels for Easy, Medium, and Hard modes, along with 21 Free To Play levels.

---

## 🧠 Puzzle Engine

The game uses a **solvability-preserving shuffle mechanism**.

Instead of randomly arranging tiles—which can produce impossible puzzle states—the application begins from a solved configuration and performs a sequence of legal random moves.

This guarantees that every generated puzzle remains reachable from the solved state.

### Move Validation

A tile can move only when it is **orthogonally adjacent** to the empty position.

The game validates the selected tile's row and column against the empty cell before performing the move.

### Scoring

The implemented scoring formula is:

```text
S = max(0, round(100 - 0.25M - 0.05T))
```

Where:

* `S` = Score
* `M` = Number of moves
* `T` = Elapsed time in seconds

The scoring system rewards players for solving puzzles using fewer moves and less time.

---

## 🏗️ System Architecture

The application follows a modular Flutter architecture consisting of:

```text
Think and Slide
│
├── Screens
│   ├── Splash / Loading
│   ├── Authentication
│   ├── Home
│   ├── Difficulty Selection
│   ├── Level Selection
│   ├── Gameplay
│   ├── Pause
│   ├── Congratulations
│   ├── Daily Streak
│   ├── Global Ranking
│   └── Settings
│
├── Widgets
│   └── Reusable UI Components
│
├── Services
│   ├── Authentication
│   ├── Firestore
│   ├── Audio
│   ├── Streak
│   └── Theme Persistence
│
├── Assets
│   ├── Puzzle Images
│   ├── Backgrounds
│   └── Music
│
└── Firebase
    ├── Authentication
    ├── Cloud Firestore
    └── Analytics
```

The project separates presentation, reusable UI components, application services, game logic, persistence, and assets to improve maintainability.

---

## 🛠️ Technology Stack

| Technology                  | Purpose                                     |
| --------------------------- | ------------------------------------------- |
| **Flutter**                 | Cross-platform mobile application framework |
| **Dart**                    | Application and game logic                  |
| **Firebase Authentication** | User authentication                         |
| **Cloud Firestore**         | Cloud data storage and synchronization      |
| **SharedPreferences**       | Local persistence                           |
| **Firebase Analytics**      | Application analytics                       |
| **Google Sign-In**          | Google authentication                       |
| **AudioPlayers**            | Background music and audio                  |
| **Google Fonts**            | Typography and UI styling                   |

The project uses Firebase Core, Firebase Auth, Cloud Firestore, Firebase Analytics, Google Sign-In, SharedPreferences, AudioPlayers, and Google Fonts.

---

## 💾 Data & Persistence

Think and Slide uses a **local-first gameplay model**.

### SharedPreferences

Used for:

* Completed levels
* Per-level moves and time
* Scores
* Daily streak
* Theme selection
* Music volume
* Mute status
* Vibration settings
* Guest state
* Cached progress

### Firebase Authentication

Used for:

* Google-based authentication
* Authentication state
* Account-based access

### Cloud Firestore

Used for:

* User profiles
* Total scores
* Level-specific progress
* Global ranking

Authenticated users can synchronize their locally stored progress with the cloud.

---

## 🎮 Gameplay Flow

```text
Launch Application
        ↓
Splash / Loading
        ↓
Login or Guest Access
        ↓
Username Setup
        ↓
Home Screen
        ↓
Difficulty Selection
        ↓
Level Selection
        ↓
Puzzle Gameplay
        ↓
Win Detection
        ↓
Score Calculation
        ↓
Progress Saved
        ↓
Next Level / Home
```

The application also provides dedicated screens for daily streaks, global rankings, and settings.

---

## 📱 Application Highlights

### Puzzle Gameplay

Players solve image-based sliding puzzles while the application tracks:

* Time
* Number of moves
* Score
* Level completion

Invalid tile selections do not modify the board, while valid moves update the board and can trigger configured vibration feedback.

### Daily Streak

Players can maintain a consecutive-day puzzle-solving streak to encourage continued engagement.

### Global Ranking

Authenticated players are ranked according to their total score stored in Cloud Firestore.

### Personalization

Players can customize:

* Visual theme
* Music volume
* Mute settings
* Vibration feedback

---

## 🔒 Authentication

The application supports two primary access paths:

```text
                ┌── Google Sign-In
Authentication ─┤
                └── Guest / Local Play
```

Firebase Authentication manages account access, while guest users can play locally without requiring authentication.

---

## 🧪 Testing & Evaluation

Functional testing covered the major user journey, including:

* Application launch
* Authentication and guest access
* Difficulty selection
* Level selection
* Puzzle movement
* Win detection
* Score calculation
* Progress persistence
* Cloud synchronization
* Global ranking
* Settings
* Daily streak

The report describes the completed implementation as a feature-rich casual puzzle application rather than a standalone puzzle board.

---

## 🚀 Getting Started

### Prerequisites

Make sure you have:

* Flutter SDK
* Dart SDK
* Android Studio
* Android SDK
* A configured Firebase project

### Clone the Repository

```bash
git clone <YOUR-REPOSITORY-URL>
cd think-and-slide
```

### Install Dependencies

```bash
flutter pub get
```

### Configure Firebase

Add the appropriate Firebase configuration for your Android application.

### Run the Application

```bash
flutter run
```

---

## 📂 Project Structure

A simplified project structure:

```text
lib/
├── screens/
├── widgets/
├── services/
├── theme/
└── main.dart

assets/
├── Easy/
├── Medium/
├── Hard/
├── free to play/
├── backgrounds/
└── music/
```

The report specifies a source organization based around screens, widgets, services, theme management, and dedicated asset directories.

---

## 🔮 Future Development

Potential future improvements include:

* Larger puzzle sizes
* Custom image importing
* Additional themes
* Hint system
* Undo functionality
* Additional sound-effect packs
* Improved tile transitions
* Accessibility features
* Advanced achievement systems
* Difficulty-aware score normalization
* Server-side leaderboard validation
* Seasonal rankings
* Cloud-based puzzle content
* Expanded Android device testing

These directions are identified in the project report as possible future extensions.

---

## 🎓 Academic Project

**Think and Slide** was developed as a Software Development Project for the **Bachelor of Science in Computer Science and Engineering** program at **Bangladesh University of Business and Technology (BUBT)**.

### Development Team

* **Syed Sami Sayem**
* **MD Tanvir Islam**
* **Raisa Sadik Smrity**
* **Sourav Chandra Shil**
* **Tasmia Anwar Nisa**

The project was completed in **August 2026**.

---

## 📄 Documentation

For detailed information about the system architecture, requirements, implementation, database design, testing, limitations, and future development, refer to the project report included in this repository.

---

## 📜 License

This project was developed as an academic software development project. Please review the repository's licensing and asset usage terms before redistribution or commercial use.

---

<p align="center">
  <b>Think and Slide</b><br>
  A simple puzzle. A thoughtful challenge. A complete mobile experience.
</p>
