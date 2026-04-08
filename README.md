# SignSync ✌️

A real-time ASL (American Sign Language) translator that works both ways — sign language to English and English to sign language — with a Gen Z aesthetic.

## Features

### Sign → Text
- Uses your webcam to detect hand shapes in real-time
- Powered by **MediaPipe Hands** (21-point hand landmark tracking)
- Classifies ASL letters A–Z from finger positions
- Builds words letter by letter with live confidence display
- Space, backspace, copy, and text-to-speech controls

### Text → Sign
- Type any word or sentence
- Animates through each letter as an ASL fingerspelling sequence
- Quick-phrase chips including Gen Z slang (no cap, slay, vibe check...)
- Auto-play with adjustable speed, manual step-through, and progress dots

### Voice → Sign
- Tap the mic and speak naturally
- Live speech transcription using the **Web Speech API**
- Signs animate automatically as you speak
- Waveform and pulsing ring animations while listening
- Adjustable sign speed slider (0.3s – 1.5s per letter)
- Tap history pills to replay any previous phrase

### ASL Guide
- Full A–Z reference with hand emoji and description for each letter
- Tap any letter to instantly animate it in the translator

## Tech Stack

- Vanilla HTML, CSS, JavaScript — no frameworks, no build step
- [MediaPipe Hands](https://developers.google.com/mediapipe/solutions/vision/hand_landmarker) for hand tracking
- Web Speech API for voice recognition
- Space Grotesk font

## Getting Started

Just open `index.html` in a browser — no install needed.

For the camera and voice features, use **Chrome or Edge** and allow mic/camera permissions when prompted.

## How ASL Detection Works

MediaPipe extracts 21 3D landmarks per hand on every frame. A rule-based classifier checks:
- Which fingers are extended (tip vs PIP joint position)
- Thumb–index distance for letters like F, O, C
- Finger spread for V vs U vs K
- Horizontal vs vertical index orientation for G vs D

The model requires ~0.6 seconds of a stable pose before registering a letter, which reduces jitter from hand movement.

> **Note:** J and Z require drawing motion in standard ASL — this app detects their base static pose.

## Screenshots

| Sign → Text | Text → Sign | Voice Mode |
|---|---|---|
| Show an ASL letter to your camera | Type or speak a phrase | Speak and watch signs animate |
