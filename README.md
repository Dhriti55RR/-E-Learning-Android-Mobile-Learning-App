# 📚 E-Learning — Android Mobile Learning App

An Android e-learning application built with **Kotlin** and **Jetpack Compose** that lets users browse courses, consume articles and video lessons, take quizzes, track progress, and save personal notes — all from their phone, anytime, anywhere.

> Mini Project — Dept. of CSE, JSSATEB (2022–2023)

---

## ✨ Features

- 🔐 **User Authentication** — Sign up, log in, and password reset flow
- 📖 **Course Catalog** — Browse, search, and filter courses by category and difficulty
- 📰 **Article & Video Lessons** — Rich-text articles and embedded video content per course
- 📝 **Quizzes** — Multiple-choice quiz tests with per-question navigation and instant results (correct/incorrect indicators)
- 📊 **Progress Tracking** — Course completion status shown on the Overview page
- 🗒️ **Notes** — Add, search, edit, and delete notes tied to course content
- 📡 **Offline-ready Architecture** — Designed to support offline access to downloaded materials
- 🎯 **Personalized Recommendations** *(planned)* — Suggested courses based on user activity

---

## 📱 Screenshots

| Welcome | Login | Sign Up |
|---|---|---|
| ![welcome](docs/screenshots/welcome.png) | ![login](docs/screenshots/login.png) | ![signup](docs/screenshots/signup.png) |

| Courses | Article | Video Article |
|---|---|---|
| ![courses](docs/screenshots/courses.png) | ![article](docs/screenshots/article.png) | ![video](docs/screenshots/video.png) |

| Quiz | Quiz Results | Course Summary |
|---|---|---|
| ![quiz](docs/screenshots/quiz.png) | ![results](docs/screenshots/results.png) | ![summary](docs/screenshots/summary.png) |

| Notes | Course Overview |
|---|---|
| ![notes](docs/screenshots/notes.png) | ![overview](docs/screenshots/overview.png) |

> Add the actual screenshots from the project report into a `docs/screenshots/` folder so the table above renders correctly on GitHub.

---

## 🧭 User Flow

```
Welcome → Sign Up / Login → Courses → Course Details
        → Article → Video Article → Quiz Test → Quiz Results
        → Course Summary → Course Overview (progress tracking)
```

Notes can be added at any point along the Article, Video Article, and Quiz Results screens.

---

## 🛠️ Tech Stack

| Category | Technology |
|---|---|
| Language | [Kotlin](https://kotlinlang.org/docs) |
| UI Toolkit | Jetpack Compose (Material Design) |
| IDE | Android Studio |
| DI | Dagger-Hilt (`@AndroidEntryPoint`) |
| Navigation | Jetpack Navigation Compose |
| Architecture | MVVM (ViewModels per feature: Login, User, Programme, Course, Note) |
| Networking | Retrofit / Volley (for content & OCR-related requests) |
| OCR | Tesseract / Google Mobile Vision OCR (planned integration) |
| Auth & Cloud | Google Play Services (Sign-In, Search integration) |

---

## 🏗️ Project Structure (key modules)

```
com.example.elearningapp
├── MainActivity.kt                  # App entry point, NavHost, top/bottom bars
├── navigation/                      # Nav graphs & route destinations
├── viewmodels/                      # LoginViewModel, UserViewModel, CourseViewModel, NoteViewModel, ProgrammeViewModel
├── models/                          # CourseContent, NoteEntity, etc.
├── datasource/                      # CourseData and other data sources
├── common/                          # ActionState (loading/success/error wrapper)
└── ui/
    ├── theme/                       # ELearningAppTheme
    └── views/
        ├── login/                   # LoginScreen, LoginCard, ForgotPasswordDialog
        ├── courses/                 # CourseArticleScreen, CourseVideoArticleScreen,
        │                            # CourseQuizTestScreen, CourseQuizResultsScreen,
        │                            # CourseSummaryScreen
        ├── notes/                   # NotesOverviewScreen, NoteCard, EditNoteDialog
        └── components/              # TopBar, BottomNavBar, CourseBottomNavBar
```

### Module highlights
- **Login Module** — Handles login state, password visibility toggling, error messages, and a "Forgot Password" dialog.
- **Article Module** — Fetches and renders course article content with an async-loaded featured image and an "Add Note" action.
- **Video Article Module** — Displays a clickable video thumbnail (launches a YouTube activity) plus key-point bullet lists.
- **Course Test Module** — Renders quiz questions with radio-button options, question indicators, and Previous/Next/Answer controls.
- **Course Result Module** — Shows correct/incorrect answers with check/cross icons and lets users add notes on their results.
- **Notes Module** — Searchable note list with add/edit/delete support backed by a `StateFlow<List<NoteEntity>>`.

---

## 🚀 Getting Started

### Prerequisites
- [Android Studio](https://developer.android.com/studio) (latest stable)
- Android SDK (API level as configured in `build.gradle`)
- An Android device or emulator with a camera (for OCR-related features)

### Setup
```bash
# Clone the repository
git clone https://github.com/<your-username>/e-learning-android.git
cd e-learning-android

# Open in Android Studio
# File > Open > select the project folder

# Sync Gradle and run on an emulator/device
```

---

## 🔮 Future Enhancements

- Interactive learning activities — puzzles, simulations, hands-on exercises
- Social learning — discussion forums, group projects, live chat
- Personalized learning paths via ML-based recommendations
- Gamification — badges, leaderboards, achievements
- Adaptive learning that adjusts pace/content to performance
- AR/VR integration for immersive lessons (virtual field trips, 3D simulations)
- Learning analytics dashboard for progress and engagement insights

---

## 📚 References

- [Android Developers](https://developer.android.com)
- [Stack Overflow](https://stackoverflow.com)
- [YouTube](https://www.youtube.com)
- [Udemy](https://www.udemy.com)
- [Kotlin Documentation](https://kotlinlang.org/docs)

---

## 👥 Contributors

Dept. of CSE, JSSATEB — Mobile Application Development Mini Project (2022–2023)

## 📄 License

This project is for academic purposes. Add a license of your choice (e.g., MIT) if you plan to open-source it.
