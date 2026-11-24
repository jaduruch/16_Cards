# 16 Cards

A native Android app written in Java, with no additional runtime libraries. Four overlapping stacks of petrol-blue cards, a target number, a running total, and a stopwatch. Supports light and pure-black dark mode, plus German and English.

## Game modes

The app opens on the home screen, where you can choose a mode and adjust language and appearance.

- **5er:** Solve five targets in a row. Each correct total automatically starts the next round. The stopwatch measures the entire run.
- **10er:** The same challenge with ten targets.
- **Free play:** Solve targets at your own pace and press **New random number** for another round. Times are never saved.

Only the three fastest completed runs per mode are stored on the device and displayed on the home screen. The 5er and 10er scoreboards are kept separate. Existing longer lists are reduced to their best three times. Incomplete runs are not saved. Returning home ends the current game; active games ask for confirmation first.

## How to play

- Each stack contains four individually tappable cards with a value of 6, 7, 8, or 9.
- Tap a card to move it to the upper selection row and add its value to the total. Tap it again to return it to the lower stack and subtract its value.
- The stopwatch stops the first time you reach the target. Selected cards remain interactive.
- **Reset** returns all cards to their stacks and clears the total. It leaves the target and stopwatch unchanged, including whether the stopwatch is running or stopped.
- **New random number** resets the cards and stopwatch and starts a new round with a different target.
- Targets are chosen uniformly from 12 to 108. Every number in this range can be reached using the available cards.
- The stopwatch pauses while the app is in the background. Rotating the device preserves the round, selected cards, and elapsed time.
- The interface can be scrolled on small screens and in landscape orientation.

## Appearance and language

- Use the sun/moon icon to switch between light mode and a pure-black dark mode.
- Open the **DE / EN** dropdown to the left of the theme icon to select **Deutsch** or **English**.
- Theme and language preferences are saved for future launches. Switching either setting preserves the current game and stopwatch.

## Run in Android Studio

1. Open this folder as a project.
2. Install JDK 17 and Android SDK 35, or configure them through Android Studio.
3. Sync Gradle and select **Run** to launch the app on an emulator or Android device running Android 6.0 or later.

Alternatively, with the Android SDK and JDK 17 configured:

```sh
./gradlew assembleDebug
```

The APK is generated at `app/build/outputs/apk/debug/app-debug.apk`.

## Validation

Target reachability was checked by exhaustively enumerating all 625 combinations of card counts. The debug build has been verified successfully with `./gradlew assembleDebug`. A full visual review of both languages and themes on a device is still pending.
