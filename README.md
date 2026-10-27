# ASL Video Translator

A Python prototype for analyzing sign-language videos and generating a text interpretation. The `ASLTranslatorEnhanced` class uses MediaPipe hand and face landmarks and a Gemini model integration as part of its analysis pipeline.

## The problem it explores

Sign-language video is rich in hand movement, facial expression, and context. This project explores a model-assisted pipeline for analyzing a video and producing a text interpretation, with translation and speech-related utilities.

> **Status:** Experimental prototype. Model output is not a certified sign-language translation and must be reviewed by qualified signers.

## Main components

- Video/image processing with OpenCV and Pillow.
- Hand and face landmark detection using MediaPipe.
- Gemini API integration for model-assisted video interpretation.
- Arabic translation utilities and text-to-speech support.
- Helpers for cleaning up uploaded model files.

## Demo

No verified screenshot or sample output video is included yet. After testing with a short, consented sample clip, add a short GIF/video showing the input and the generated interpretation.

Suggested location: `assets/demo.gif` or `assets/demo.mp4`.

## Tech stack

Python · OpenCV · MediaPipe · Google Gen AI SDK · Pillow · deep-translator · gTTS

## Setup

Use a Python version compatible with the pinned dependencies.

```bash
python -m venv .venv
# Windows:
.venv\Scripts\activate
# macOS/Linux:
# source .venv/bin/activate

pip install -r requirements.txt
```

## Configure the Gemini API key

The class accepts a key explicitly:

```python
from STT import ASLTranslatorEnhanced

translator = ASLTranslatorEnhanced(gemini_api_key="LOAD_YOUR_KEY_SECURELY")
```

Replace the example string with a key loaded securely from an environment variable or secret manager. Never commit a real API key. The current fallback in `STT.py` references a machine-specific Windows path and should be replaced with portable configuration before sharing the project.

## Run

`python STT.py` currently defines the class but does not launch a complete interactive application. Create a separate demo script that loads a short video, initializes the translator with a securely configured key, and calls the relevant public video-processing method. Check the available methods in [STT.py](./STT.py) before building the script.

## Limitations and privacy

- Model interpretations may be inaccurate or miss context.
- ASL is distinct from Arabic/Jordanian Sign Language and other sign languages.
- Use only video you have permission to process. Videos may contain identifying or biometric information.
- Confirm temporary and remotely uploaded files are cleaned up appropriately.

## Roadmap

- [ ] Replace the machine-specific API key fallback with environment-variable configuration.
- [ ] Add a tested example script and clear input/output format.
- [ ] Include a real demo clip and sample output using consented data.
- [ ] Add tests and error handling for invalid video, API failures, and unsupported formats.
- [ ] Document latency, model limitations, and supported Python versions.
