# smoke and mirrors 💨

Blow fake smoke at your webcam.

Hold two fingers up like you're holding a cigarette and one appears between them. Bring it to your lips and the ember glows. Open your mouth and you exhale a cloud. The longer you "drag", the bigger the cloud.

**Try it:** https://tanisha-byte.github.io/smoke-and-mirrors/

## How it works

- [MediaPipe](https://developers.google.com/mediapipe) face and hand landmarkers run in the browser (WebAssembly, GPU when available).
- Face landmarks find your mouth; the `jawOpen` blendshape decides when you're exhaling.
- Hand landmarks place the cigarette between your index and middle fingers and point the filter toward your mouth.
- Smoke is a few thousand soft sprites drawn on a canvas, nudged by a cheap fake turbulence.

The whole thing is one `index.html`. No build step, no backend.

## Privacy

Your camera feed never leaves your device. The page downloads the tracking models from Google's CDN and does everything else locally. Nothing is recorded or uploaded.

## Run it locally

Browsers only allow camera access over HTTPS or on `localhost`, so serve the folder rather than opening the file directly:

```sh
python3 -m http.server 8000
# then open http://localhost:8000
```

No camera, or you denied access? Press and drag anywhere on the screen to blow smoke with your finger or mouse.

## Browser support

Recent Chrome, Edge, Safari (macOS and iOS 16.4+) and Firefox. Phones work; the front camera is used.

## Disclaimer

It's a toy. No actual cigarettes were harmed, and none are recommended.

## License

[MIT](LICENSE)
