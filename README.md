# Mad Minute (Android)

Ivana's 30-fact multiplication drill. 1-, 1½- or 2-minute timer, "tough ones" mode for 6s–9s,
missed facts come back more often, score history saved on the phone.

## Self-updating
On every launch the app downloads the latest page from:

https://raw.githubusercontent.com/devsenweb/mad-minute/main/app/src/main/assets/index.html

Edit `app/src/main/assets/index.html` and get it onto `main`. The phone picks it up
the next time the app opens (right away if Ivana is on the home screen). No reinstall.

## Get the APK
Every push that changes the app code runs the "Build Mad Minute APK" workflow (`.github/workflows/apk.yml`), which attaches the
APK to the `latest` release:

https://github.com/devsenweb/mad-minute/releases/download/latest/MadMinute.apk

Open that on the Android phone, tap the download, and allow "Install unknown apps" when asked.

Pushing only `index.html` changes does not rebuild the APK (no need). Code changes rebuild it,
and the fixed signing key (`app/madminute.keystore`) lets the new APK install over the old one.
