# PHANTOM

A browser-based hand-gesture particle interface with full-body pose tracking and facial-expression visualisation. Camera access starts only after you click **ACTIVATE SYSTEM**. Hand, pose, and face landmarks are processed in your browser; PHANTOM does not upload camera frames to its own server.

## Start it

Use the HTTPS URL shown under the repository's **Settings → Pages**, or run it locally over localhost. With Python installed:

```bash
py -m http.server 8000
```

Then open http://localhost:8000.

## Full-body and face tracking

When the camera is activated, PHANTOM loads MediaPipe tasks for hands, pose, and face:

- **Body skeleton:** tracks visible head, shoulders, elbows, wrists, torso, hips, knees, ankles, heels, and foot points (33 pose landmarks).
- **Face outline:** displays face contour, brows, eyes, and lip landmarks.
- **Expression estimates:** uses facial blendshape scores to estimate visible cues including smiling, frowning, surprise-like wide eyes/open mouth, blinking, raised brows, squinting, puckering, and pressed lips. Scores for smile, jaw opening, brows, and blinking are shown in the live preview. These are visual estimates, not a reading of someone's thoughts or feelings.
- **Live skeleton overlay:** the small mirrored camera preview shows detected joints with a cyan/violet skeleton and current body/face status.

### Get easier body tracking

1. Click **ACTIVATE WITH CAMERA** and allow camera permission.
2. Place your camera far enough away to see your head, shoulders, hips, knees, and feet in the live preview.
3. Use even light on your face and body; avoid a very bright window behind you.
4. Keep moving naturally, but give the detector a moment to acquire the whole pose.
5. For expression tracking, keep your face visible and large enough for the face landmarks.

The app uses a 960×540 ideal camera request to balance responsiveness and detail. Your browser may select another supported resolution. Pose/face inference runs at a lower rate than hand tracking to reduce load. Models and the WASM runtime are fetched from public CDNs / model hosting on first use, so an internet connection is required.

## Gesture powers

- **Open palm:** steer the energy field.
- **Pinch and release:** grab nearby particles and throw them.
- **Fist, then open:** compress the core and release a burst.
- **Point with one finger:** fire a photon beam.
- **Two hands:** expand the core by moving your hands apart.
- **Fast hand swipe:** release an energy slash.
- **Two-finger V sign:** open a rotating vortex portal.
- **Thumb up:** activate an energy shield that pushes particles away.

## Deployment

1. Open repository **Settings → Pages**.
2. Under Build and deployment, choose **Deploy from a branch**.
3. Select branch `main` and folder `/(root)`, then save.
4. Wait for the latest Pages build to succeed, then open the published URL.

## Troubleshooting

- Open the GitHub Pages HTTPS URL, not the raw HTML file.
- If the body label reads **BODY PARTIAL**, step back or reposition your camera so more of your body fits in frame.
- If the face label reads **NO FACE**, move into better lighting and make sure your face is visible in the preview.
- If body or face status reads **MODEL OFFLINE**, check internet access and reload so the model can download.
- Allow camera permission and close other apps that may be using the webcam.
- Use **STOP CAMERA** to end the camera stream. **MOUSE TEST** remains available for testing the particle controls without a webcam.
