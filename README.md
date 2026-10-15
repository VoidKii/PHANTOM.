# PHANTOM

A browser-based hand-gesture particle interface with real-time effects. Webcam access starts only after you click **ACTIVATE SYSTEM**. Hand landmarks are processed locally in your browser; camera frames are not uploaded to a PHANTOM server.

## Start it

Open the live GitHub Pages URL shown under **Settings → Pages**, or run it locally over HTTPS/localhost. With Python installed:

```bash
py -m http.server 8000
```

Then open http://localhost:8000.

## Gesture powers

- **Open palm:** steer the energy field.
- **Pinch and release:** grab nearby particles and throw them.
- **Fist, then open:** compress the core and release a burst.
- **Point with one finger:** fire a photon beam.
- **Two hands:** expand the core by moving your hands apart.
- **Fast hand swipe:** release an energy slash.
- **Two-finger V sign:** open a rotating vortex portal.
- **Thumb up:** activate an energy shield that pushes particles away.

## Make tracking easier

1. Click **ACTIVATE WITH CAMERA** and allow camera permission.
2. Use the small **LIVE VISION** preview. Keep the whole hand inside the frame; the cyan landmark skeleton shows when PHANTOM sees it.
3. Use steady, even light and keep the palm a comfortable distance from the camera.
4. Start with one hand. Use two hands only for core expansion.
5. If the hand is lost, move it back into the preview and pause briefly. Detection confidence is tuned for easier pickup.

The app uses a 960×540 ideal camera request to balance detail and responsiveness. Your browser may select a different supported resolution. Hand tracking uses MediaPipe Tasks Vision and a model loaded from public CDNs, so an internet connection is needed. Use **STOP CAMERA** to end the stream. **MOUSE TEST** remains available without a webcam.

## Deploy with GitHub Pages

1. Open repository **Settings → Pages**.
2. Choose **Deploy from a branch** under Build and deployment.
3. Select branch `main` and folder `/(root)`, then save.
4. Wait for the Pages build to succeed, then use the URL shown by GitHub.

## Troubleshooting

- If the camera does not start, open the GitHub Pages HTTPS URL rather than the raw HTML file.
- If tracking stays in searching mode, make sure the LIVE VISION preview shows the full hand and check the browser's camera permission.
- If the model cannot load, check your connection because the hand-tracking module, WASM files and model are loaded online.
- Close other apps that may be using the webcam.
