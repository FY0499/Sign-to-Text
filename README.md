# Sign-to-Text

A sign-language translation system that helps people who use sign language communicate with people who do not understand it. The user performs signs in front of the camera, and the system analyzes the video, turns the signs into text, and provides spoken output so the other person can understand the message.

## How it works

1. The camera captures the sign-language movements.
2. MediaPipe detects hand and face landmarks in the video frames.
3. Gemini analyzes the video and generates a text interpretation.
4. The result can be translated into Arabic and played as audio.

## Features

- Hand and face landmark detection.
- Video analysis using Gemini.
- Text interpretation and Arabic translation.
- Audio output for spoken communication.
- Flutter frame-processing integration.

## Technologies

Python, OpenCV, MediaPipe, Google Gen AI SDK, Pillow, deep-translator, and gTTS.

## Setup

```bash
git clone https://github.com/FY0499/Sign-to-Text.git
cd Sign-to-Text
python -m venv .venv
pip install -r requirements.txt
```

Initialize the translator with your Gemini API key:

```python
from STT import ASLTranslatorEnhanced

translator = ASLTranslatorEnhanced(gemini_api_key="YOUR_GEMINI_API_KEY")
```

The main implementation is in [STT.py](./STT.py).
