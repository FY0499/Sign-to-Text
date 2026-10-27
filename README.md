# ASL Video Translator

A Python prototype for analyzing sign-language videos and generating a text interpretation. The `ASLTranslatorEnhanced` class uses MediaPipe hand and face landmarks and a Gemini model integration as part of its analysis pipeline.

## Key components
- Video/image processing with OpenCV and Pillow.
- Hand and face landmark detection using MediaPipe.
- Gemini API integration for model-assisted video interpretation.
- Arabic translation utilities and text-to-speech support.
- Cleanup helpers for uploaded model files.

## Tech stack
Python, OpenCV, MediaPipe, Google Gen AI SDK, Pillow, deep-translator, and gTTS.

## Requirements
Python dependencies are listed in [requirements.txt](./requirements.txt).

## Setup
1. Create and activate a virtual environment using a Python version compatible with the pinned dependencies.
2. Install dependencies: `pip install -r requirements.txt`
3. Configure a valid Gemini API key locally. The implementation accepts `gemini_api_key` in `ASLTranslatorEnhanced(gemini_api_key=...)`; its fallback currently references a machine-specific local file path, which must be changed for use on another machine.
4. Never commit the API key or the local API key file.
5. Review [STT.py](./STT.py) for the class API and test with a short, non-sensitive video.

## Limitations
Sign-language interpretation is complex and context-dependent. Model-generated interpretations can be inaccurate, and ASL is not interchangeable with other sign languages. Treat output as experimental and have qualified signers review results before any real-world use.

## Security and privacy
Video can contain biometric and identifying information. Use consented test material, protect uploaded files, and ensure temporary or remote files are cleaned up appropriately.

## Project status
Prototype implementation. Verify model availability, API access, supported video formats, and end-to-end behavior in your environment.
