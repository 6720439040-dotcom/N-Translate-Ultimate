# N-Translate Ultimate

Android screen OCR translator prototype for personal use. Target: Samsung Galaxy S24 Ultra.

## Features in this starter build
- First-run PIN setup and local PIN gate.
- Android MediaProjection screen capture (user consent required).
- Floating `N` toggle and translation panel.
- On-device ML Kit text recognition, language identification and translation.
- English, Japanese, Chinese, Korean, French, German, Spanish, Italian, Portuguese and Russian source-language mapping to Thai.
- GitHub Actions workflow builds a debug APK.

## Important limitations
- This is a functional starter implementation, not a polished release.
- The current OCR processing pass uses the Latin recognizer. Japanese/Chinese/Korean recognizer dependencies are included for the next OCR routing enhancement; manga layout, vertical text and speech-only video are not fully supported yet.
- Video with visible subtitles can be read as screen text. Speech without subtitles needs a separate speech-recognition pipeline.
- Android/DRM protected apps may block screen capture and show black frames.
- ML Kit translation models are downloaded to the device on first use. Internet is needed for initial model download; translation runs on-device afterward. No paid API key or monthly API subscription is used.
- Translation quality and supported source languages depend on the installed ML Kit model.
- The PIN is a local app gate, not tamper-proof device licensing. It does not securely bind the APK to one handset. For stronger protection, use Android Keystore and Play Integrity in a later release.
- This build has no signing/release keystore. GitHub produces a debug APK for installation/testing.

## Build on GitHub
1. Create a GitHub repository named `N-Translate-Ultimate`.
2. Upload all project files preserving folders.
3. Open **Actions** and enable workflows if GitHub asks.
4. Select **Build N-Translate Ultimate APK** then **Run workflow**, or push to `main`.
5. Open the completed run, download artifact `N-Translate-Ultimate-debug`, and extract `app-debug.apk`.
6. Transfer the APK to your S24 Ultra and install it. Android may ask permission to install unknown apps for the app you used to open the APK.

## First run
1. Launch app and set a PIN (4+ digits).
2. Tap **อนุญาตหน้าต่างลอย** and enable display over other apps.
3. Tap **เริ่มแปลหน้าจอแบบ Live** and approve screen capture.
4. Open a game/video/manga page. The translation panel appears at the bottom. Tap floating N to hide/show it.
5. Stop using the app's **หยุดบริการแปล** button.

## Privacy
Screen frames are processed locally in the app. ML Kit model download requires network access. This starter does not upload captured screenshots to a custom server.
