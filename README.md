# Beer / Time — GitHub Pages edition

A static hand-tracking beer experiment. English by default, with Thai available in the language selector. Raise a pinched hand to fill, lower to rewind, release to freeze, and swipe an open palm left for the next glass. Filling beyond 100% reveals the real overflow footage, up to 150%.

## Publish on GitHub Pages

1. Extract this ZIP.
2. Upload **all extracted files and the vendor folder** to the root of your GitHub repository. `index.html` must be directly in the repository root, not inside another folder. Upload the extracted files, not the ZIP itself.
3. Open the repository's **Settings → Pages**.
4. Under **Build and deployment**, select **Deploy from a branch**.
5. Select your branch (usually `main`) and **/(root)**, then **Save**.
6. Once deployment finishes, open the site URL shown in Pages settings. Allow camera access when you choose Enable hand tracking.

Official setup guide: https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site

## Files

- `index.html`: all interface HTML, CSS, and application JavaScript in one file.
- `beer-overflow.mp4`: source footage used for filling and overflow.
- `empty-glass.png`, `full-glass.png`: visual assets.
- `vendor/`: local MediaPipe library, WebAssembly runtime, and hand model.
- `.nojekyll`: serve this as a plain static site.

Keep these filenames and relative folder locations intact. The HTML needs the accompanying assets; it is not a fully standalone offline HTML file. No npm, build step, Python server, or API key is required on GitHub Pages. All individual files are below 25 MB.

Camera processing happens on the device. Videos selected through the page stay in that browser session. Use the HTTPS Pages URL, not GitHub's source-file or raw-file preview, for camera access.

The generated empty glass is composited with the supplied footage below full; the overflow uses the original clip. This is not a physics simulation. The overflow challenge is calibrated to the included clip; other uploaded clips use a user-set 0–100% time range.

MediaPipe Tasks Vision 0.10.21: https://github.com/google-ai-edge/mediapipe
Hand Landmarker model: https://storage.googleapis.com/mediapipe-models/hand_landmarker/hand_landmarker/float16/1/hand_landmarker.task

## วิธีลงแบบย่อ

แตก ZIP แล้วอัปโหลดทุกไฟล์พร้อมโฟลเดอร์ vendor ลงหน้าแรกของ repository จากนั้น Settings → Pages → Deploy from a branch → main → /(root) → Save เปิดเล่นผ่านลิงก์เว็บไซต์ที่ GitHub Pages แสดงให้ และอนุญาตกล้องเมื่อกดเปิดใช้งาน
