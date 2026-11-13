# JollyPhonics Pro – Android Phonics Learning Application

**Student:** Faheem Pasha Guled  
**USN:** 25MCAR0157  
**Course:** Mobile Application Development Lab

## 1. Project overview

JollyPhonics Pro is a beginner-friendly Android application that helps children and English beginners practise the sounds associated with the 26 letters of the English alphabet. A learner selects a letter, sees an example word, listens to a phonics cue and the example word, and can record and replay their own pronunciation.

## 2. Problem statement

Children and beginners may find it difficult to connect written English letters with their sounds. JollyPhonics Pro combines a visual alphabet grid, spoken phonics examples and voice practice in one simple application.

## 3. Objectives

- Display all 26 English letters in an easy-to-use grid.
- Show an example word for the selected letter.
- Speak a short phonics cue followed by the example word.
- Request microphone permission at runtime before recording.
- Record the learner's pronunciation and save it locally.
- List saved clips and play them when selected.

## 4. Features

1. **Alphabet grid:** A–Z displayed in a five-column `GridView`.
2. **Letter selection:** Selecting a letter updates the large letter, example word and phonics cue.
3. **Phonics playback:** Android `TextToSpeech` speaks the cue and example word. The app uses `QUEUE_FLUSH` to replace previous speech rather than queueing repeated utterances.
4. **Voice recording:** `MediaRecorder` captures the learner's voice after runtime microphone permission is granted.
5. **Local recording list:** Saved `.m4a` files are listed in a `ListView`.
6. **Recording playback:** Tap a saved item to play it using `MediaPlayer`.
7. **Cinematic UI:** Gradient background, contrasting panels and styled buttons.
8. **Student identification:** Student name and USN are shown in the app footer for the required evidence screenshot.

## 5. Technology and Android concepts

| Technology / concept | Purpose in this project |
|---|---|
| Java | Application logic |
| Android Studio | Development environment |
| XML layouts and drawable resources | Screen layout and visual styling |
| `GridView` | Display the 26 letters |
| `TextView` | Display selected letter, word, cue and status |
| `TextToSpeech` | Speak the phonics cue and example word |
| `MediaRecorder` | Record the learner's voice |
| `MediaPlayer` | Play a saved recording |
| `ListView` / `ArrayAdapter` | Display saved recordings |
| Runtime permission API | Request `RECORD_AUDIO` access |
| App-specific external files directory | Store recordings locally in the app's private area |

## 6. Demonstration scenario

1. Launch JollyPhonics Pro.
2. Select **B** from the alphabet grid.
3. Confirm that the selected letter and the example word **Ball** are displayed.
4. Tap **PLAY SOUND & WORD** and listen to the phonics cue and example word.
5. Tap **Record**. On the first attempt, grant microphone permission when Android asks.
6. Tap **Record** again if the permission prompt just completed, then say “B for Ball” for two or three seconds.
7. Tap **Stop & Save**.
8. Under **My Recordings**, tap the new recording to play it.

## 7. How to open and run

1. Extract the ZIP archive.
2. Open the `JollyPhonics_Pro` folder in Android Studio (**File → Open**).
3. Allow Android Studio to complete Gradle sync. The project uses Android Gradle Plugin `8.6.1`, compile SDK `35`, and Java source code.
4. Install the Android SDK Platform 35 if Android Studio prompts for it.
5. Connect an Android phone with USB debugging enabled, or start an emulator with microphone input enabled.
6. Click **Run ▶** and select the device.
7. Grant microphone permission when prompted.

> The project archive does not include a prebuilt APK. Build and run it from Android Studio. A physical Android phone is recommended for testing microphone input; emulator microphone support depends on emulator settings and the host computer.

## 8. Project folder structure

```text
JollyPhonics_Pro/
├── app/
│   ├── build.gradle
│   └── src/main/
│       ├── AndroidManifest.xml
│       ├── java/com/example/jollyphonics/
│       │   └── MainActivity.java
│       └── res/
│           ├── drawable/       # Backgrounds, buttons and letter tile shapes
│           ├── layout/         # Main screen and alphabet cell layouts
│           └── values/         # App theme and styles
├── docs/
│   ├── TEST_CASES.md
│   └── SUBMISSION_CHECKLIST.md
├── screenshots/                # Add real emulator/device evidence here
├── build.gradle
├── gradle.properties
├── settings.gradle
├── .gitignore
└── README.md
```

## 9. Test evidence

Add genuine screenshots captured from the running app to the `screenshots/` folder. The required filenames and capture instructions are listed in [`docs/TEST_CASES.md`](docs/TEST_CASES.md). Do not use mockups or edited images as proof of a successful test.

## 10. Limitations and notes

- Phonics pronunciation uses the English voice installed on the Android device. Speech quality and availability can vary by device and TTS engine.
- Recordings are stored locally in the app-specific storage area. They are not uploaded to a server.
- The recording list is populated from existing `.m4a` files when the app starts and after a new recording is saved.
- A recording should be at least one or two seconds long; very short or empty recordings may fail to save.

## 11. Author

**Faheem Pasha Guled**  
**USN: 25MCAR0157**
