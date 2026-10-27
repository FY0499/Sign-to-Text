# Sign-to-Text
A Python experimental prototype for analyzing sign-language videos and generating a text interpretation. It uses MediaPipe hand and face landmarks alongside a Gemini model integration as part of its video-analysis pipeline.

## Problem it addresses

Sign language conveys meaning through hand movement, facial expression, and context. This project explores a model-assisted workflow for interpreting a video and producing text that can support further translation or speech output.

> **Status:** Experimental prototype. Model-generated interpretations are not certified sign-language translations and must be reviewed by qualified signers.

## Main components

- Video and image processing with OpenCV and Pillow.
- Hand and face landmark detection with MediaPipe.
- Gemini API integration for model-assisted video interpretation.
- Arabic translation utilities and gTTS support.

## Demo

A verified screenshot or sample output video is not currently included. After testing with a short, consented clip, add a real GIF or video under `assets/demo.gif` or `assets/demo.mp4` and embed it here.

## Technologies

Python, OpenCV, MediaPipe, Google Gen AI SDK, Pillow, deep-translator, and gTTS. See [requirements.txt](./requirements.txt) for dependencies.

## Installation

```bash
git clone https://github.com/FY0499/STT.git
cd STT
python -m venv .venv
```

Windows:
```powershell
.venv\Scripts\Activate.ps1
pip install -r requirements.txt
```

macOS/Linux:
```bash
source .venv/bin/activate
pip install -r requirements.txt
```

## Configure the Gemini API key

The class accepts an API key explicitly. Load your key securely from an environment variable or secret manager and never commit a real key.

```python
from STT import ASLTranslatorEnhanced

translator = ASLTranslatorEnhanced(gemini_api_key="LOAD_YOUR_KEY_SECURELY")
```

The string above is a placeholder, not a working credential. The current `STT.py` implementation also references a machine-specific Windows path as a fallback; make the configuration portable before using the project on another machine.

## Usage status

The current `STT.py` defines a class but does not launch a complete interactive application. Consequently, `python STT.py` should not be presented as a finished demo. Inspect the available public methods in [STT.py](./STT.py) and create a separate tested script that loads a short video, initializes the translator securely, and calls the appropriate video-processing method.

## Limitations and privacy

- Model interpretations may be inaccurate or miss linguistic context.
- ASL is distinct from Arabic/Jordanian Sign Language and other sign languages.
- Use only video you have permission to process; video may contain identifying or biometric information.
- Verify how temporary files and remotely uploaded data are handled.

## Future improvements

- Replace the machine-specific API-key fallback with portable configuration.
- Add a tested example script and clearly document input/output formats.
- Include a real demo using consented sample data.
- Add tests for invalid videos, API failures, and unsupported formats.
- Document latency and model limitations.
