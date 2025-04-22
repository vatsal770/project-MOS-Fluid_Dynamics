# project-MOS-Fluid_Dynamics

# agentic_AI_system

An intelligent and interactive Streamlit-based web application that allows users to upload files, automatically **transcribe**, **analyze**, and **extract summaries, decisions, follow-ups**, and more using **Whisper (OpenAI)** and **gemini-2.0-flash-exp** from Google.

### Interface View
![upload interface](images/upload-interface.png)

## Features

- 🔊 **Audio Transcription** using Whisper ASR
- 📹 **Video Understanding** via Gemini model with file upload
- 🤖 Detailed AI-generated insights:
  - Summary
  - Action items & decisions
  - Follow-up tasks
  - Confidence checks
  - Domain/topic detection
- 📝 User-customizable prompt after initial analysis
- 📥 Support for `.mp3`, `.wav`, `.ogg`, `.mp4`, `.mov`, `.avi`
- 🌐 Lightweight and Docker-ready deployment

---

## 🧠 Audio2Text Conversion — Whisper by OpenAI

Whisper is a general-purpose speech recognition model trained on a large dataset of multilingual and multitask supervised data collected from the web.

### ✅ Why Whisper?

- **Multilingual Support:** Transcribe audio in English, Hindi, French, and more
- **Robustness:** Handles background noise and varied speech patterns
- **Streaming & Timestamped Output:** Easy to extract actionable insights
- **Lightweight Versions:** Supports "tiny" models that are fast and work on CPU

### 🔄 Whisper vs Other ASR Models

| Model           | Multilingual | Speed (tiny) | Accuracy | Timestamps | GPU Recommended |
|----------------|--------------|--------------|----------|------------|------------------|
| **Whisper**     | ✅ Yes       | ⚡ Fast       | 🔥 High   | ✅ Yes      | ❌ Optional      |
| Wav2Vec2 (HF)   | ⚠️ Limited   | 🐢 Medium     | ✅ Good   | ❌ No       | ✅ Yes           |
| Google Speech API | ✅ Yes     | ✅ Fast       | ✅ Good   | ❌ No       | ☁️ Cloud-only    |

---

## 🌟 Gemini 1.5 Pro — Why This Model?

Gemini 1.5 Pro is one of the most **advanced multimodal LLMs** that supports **video, text, audio, and image** inputs. It allows deeper reasoning and longer context windows, making it a perfect fit for analyzing full-length videos or rich transcriptions.

### ✅ Why Gemini?

- 🔍 **Long Context:** Handle long audio/video inputs easily
- 🔗 **Multimodal Capability:** Seamlessly processes both text and video
- 🧠 **Advanced Reasoning:** Extract decisions, summarize, detect intent, and more
- 🛠️ **Integrates with Tools:** Like DuckDuckGo for supplemental info

### 🔄 Gemini vs Other LLMs

| Model         | Multimodal | Context Length | Reasoning | Video Support | Real-time Capable |
|---------------|------------|----------------|-----------|----------------|-------------------|
| **Gemini 1.5 Pro** | ✅ Yes     | 🔁 Long (1M tokens) | 🧠 Strong | ✅ Yes         | ✅ Yes            |
| GPT-4 (OpenAI) | 🟡 Partial | 🔁 Medium        | 🧠 Strong | 🛑 No           | ✅ Yes            |
| Claude 3       | ✅ Yes     | ✅ Long          | 🧠 Good   | 🟡 Limited      | ✅ Yes            |

---

## 📸 App Interface (Screenshots)

### 📤 File Upload (Audio/Video)
![upload interface](images/upload-interface.png)

### 🧠 AI-Generated Insights
![summary result](images/summary-insights.png)

### 🗨️ User Prompt for Deeper Analysis
![custom prompt](images/user-prompt.png)

---

## 🛠️ How It Works

1. **Upload File**: User selects Audio or Video and uploads a file.
2. **Initial Processing**:
   - Audio: Transcribed via Whisper
   - Video: Uploaded and pre-processed for Gemini
3. **Gemini Agent Response**:
   - Generates structured insights:
     - 📋 Summary
     - ✅ Action items / decisions
     - 📅 Follow-ups
     - 📊 Confidence level
     - 🔍 Domain detection
4. **User Prompt (Optional)**: Allows further custom questioning after initial analysis.

---

## 📦 Installation & Run

### 🚀 Run with Docker
```bash
docker build -t multimodal-agent-app .
docker run -p 8501:8501 multimodal-agent-app
