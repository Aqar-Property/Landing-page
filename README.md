# Aqar — Landing Page

The public landing page for **عقار / Aqar Property**, in its launch state.

- `index.html` — the page itself: launch hero ("بيتك القادم يبدأ من عقار"), a live
  search demo that filters sample listings in the browser, features, steps,
  download links, FAQ, and an Arabic/English + dark/light language and theme switch.
- `app/` — the Flutter web build (`flutter build web --release`), served at `/app/`.
- `releases/latest/Aqar.apk` — signed arm64 Android build.
- `releases/latest/Aqar-32bit.apk` — signed armeabi-v7a build for older devices.
- `assets/images/` — listing photography used by the hero and the demo.
- `Materials/`, `fonts/` — brand assets and the Cairo web fonts.

## Updating the release

```bash
cd <Aqar-App>
flutter build apk --release --split-per-abi
cp build/app/outputs/flutter-apk/app-arm64-v8a-release.apk    <repo>/Landing-page/releases/latest/Aqar.apk
cp build/app/outputs/flutter-apk/app-armeabi-v7a-release.apk  <repo>/Landing-page/releases/latest/Aqar-32bit.apk
flutter build web --release
rm -rf <repo>/Landing-page/app && cp -r build/web <repo>/Landing-page/app
```

The page is a single static HTML file with inline CSS and JS; no build step or
dependencies are required to serve it. Keep the green palette (`--brand`)
unchanged when editing.
