# 🎙️ LinguaSync: Real-Time Voice Translator

[![Python](https://img.shields.io/badge/Python-3.11-blue.svg)](https://www.python.org/)
[![License](https://img.shields.io/badge/license-MIT-green.svg)](LICENSE)
[![GUI](https://img.shields.io/badge/GUI-Tkinter-orange.svg)](https://docs.python.org/3/library/tkinter.html)

**LinguaSync** is a powerful desktop application designed to bridge language barriers instantly. By leveraging deep neural networks and cloud-based APIs, it provides a seamless cross-lingual communication experience, capturing voice and delivering translated audio in real-time.

---

## 🏗️ Project Architecture

| Component | Responsibility |
| :--- | :--- |
| **`main.py`** | The core engine handling the GUI, multi-threading, and translation orchestration. |
| **`requirements.txt`** | Dependency manifest for all necessary libraries (STT, TTS, Translation). |
| **`setup.py`** | Configuration for `cx_Freeze` to build cross-platform executables. |
| **`icon.png`/`.ico`** | Visual assets for the application branding. |

---

## ⚙️ How It Works (The Logic)

The translation pipeline is a sophisticated sequence of events designed for speed and accuracy:

### 🔄 The Execution Flow

1.  **Capture** 🎤
    - The application listens via the system microphone using the `SpeechRecognition` library.
2.  **Process** 🧠
    - Audio is converted to text via **Google Web Speech API**.
    - If needed, text is **transliterated** to handle non-Latin scripts accurately.
3.  **Translate** 🌍
    - The **GoogleTranslator** (via `deep-translator`) converts the text into the target language.
4.  **Synthesize** 🔊
    - **gTTS** (Google Text-to-Speech) generates a high-quality audio file.
5.  **Output** 📝
    - The translated text is displayed in the GUI, and the audio is played back instantly.

---

## 🛠️ Tech Stack & Dependencies

| Category | Library | Purpose |
| :--- | :--- | :--- |
| **GUI Framework** | `tkinter` / `ttk` | Building the interactive desktop interface. |
| **Speech-to-Text** | `SpeechRecognition` | Interfacing with microphones and recognition engines. |
| **Translation** | `deep-translator` | High-accuracy machine translation. |
| **Text-to-Speech** | `gTTS` | Converting translated text into natural-sounding audio. |
| **Audio Playback** | `playsound` | Playing the generated `.mp3` files. |
| **Transliteration** | `google-transliteration-api` | Handling script conversions for diverse languages. |
| **Packaging** | `cx_Freeze` | Compiling the app into standalone installers. |

---

## 🚀 Key Features

- **Real-Time Processing**: Minimal latency between speaking and receiving the translation.
- **Multilingual Support**: Supports 15+ major global languages including Hindi, Spanish, Chinese, and more.
- **Voice Feedback**: Not just text—hear the translation in a natural voice.
- **Cross-Platform**: Designed to run on Windows, Linux, and macOS.
- **Threaded Execution**: Uses multi-threading to keep the UI responsive during processing.

---

## 🛠️ Installation & Usage

Refer to the [README.md](README.md) for detailed setup instructions. To get started quickly:
1. Install dependencies: `pip install -r requirements.txt`
2. Run the application: `python main.py`

---
<p align="center">Made with ❤️ for global communication.</p>
