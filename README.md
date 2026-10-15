# PHANTOM

A browser-based hand-gesture particle interface. Webcam access starts only when you click **ACTIVATE SYSTEM**. Hand landmarks are processed locally in your browser; the app does not upload camera frames to a server.

## Run locally

Open `index.html` through a local web server (camera APIs generally require localhost or HTTPS). For example, with Python installed:

```bash
py -m http.server 8000
```

Then open http://localhost:8000.

## Deploy with GitHub Pages

1. Open the repository's **Settings → Pages**.
2. Under **Build and deployment**, choose **Deploy from a branch**.
3. Select branch `main` and folder `/ (root)`, then save.
4. Open the Pages URL shown by GitHub once the deployment finishes.

## Gestures

- Move your open hand to guide the energy field.
- Pinch thumb and index finger to trigger a pulse.
- Make a fist to compress the particle field.
- Open your hand again to release it.

## Notes

The app loads MediaPipe Tasks Vision and the hand-landmarker model from their public CDNs, so an internet connection is required for first load. The browser will ask for camera permission only after activation. Use **STOP CAMERA** to end the stream. A mouse mode is available for testing without a webcam.