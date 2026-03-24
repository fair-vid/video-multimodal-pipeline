# FAIR-VID Dataset & Colab Output Structure

This document explains the directory structure used in the FAIR-VID multimodal preprocessing pipeline.

The structure is designed to support:
- Notebook-based AI agent decomposition
- Transparent data flow between agents
- Reproducible execution in Google Colab
- Easy migration to enterprise systems

---

## 🧠 Core Concept

Each **application** is processed as an independent unit:

```

<applicant_id>_<application_id>/

```

Example:
```

0_0/

```

- `0_0` → applicant_id = 0, application_id = 0
- This is typically used for **testing / demo runs**

---

## 🧪 Special ID Ranges

### Synthetic Data
```

10000000_10000001/

```
- Reserved for **synthetic / generated data**
- Used for:
  - Testing pipelines
  - Sharing reproducible examples
  - Avoiding sensitive data exposure

### Real Data
```

18190_27580/
25598_35760/
...

```
- Real applications from production systems
- Each folder corresponds to a real applicant + application

*❕ For real data testing, we strongly recommend storing all data on Google Drive in encrypted format and decrypting it exclusively at execution time.*

---

## 🤖 Agent-Based Subdirectory Design

Inside each application folder (e.g., `0_0/`), **each subdirectory corresponds to a separate AI agent**.

Example:

```

0_0/
├── documents_image/
├── documents_image_llm_text_gemma3_12b/
├── documents_image_llm_text_glm-ocr/
├── documents_image_text_pytesseract/
├── documents_image_text_pytesseract_box_info/
├── document summaries_gemma3_12b/
├── video_frame_text_gemma3_12b/
├── video_frame_text_gemma3_4b/
├── video_interviews/

```

---

## 📄 Document Processing Agents

### Raw Input
```

documents_image/

```
- Original uploaded document images (PDF/JPG/PNG)

---

### OCR-Based Agents

```

documents_image_text_pytesseract/

```
- Extracted text using Tesseract OCR

```

documents_image_text_pytesseract_box_info/

```
- OCR text **with bounding box coordinates**
- Used for:
  - Explainability
  - Visual grounding
  - Human review

---

### Vision-Language (LLM) Agents

```

documents_image_llm_text_gemma3_12b/

```
- Structured extraction using Gemma 3 (12B)

```

documents_image_llm_text_glm-ocr/

```
- Alternative OCR/LLM pipeline

```

documents_image_llm_text_gemma3_12b_doc/

```
- Document-level structured outputs (JSON-style)

---

### Summarization Agent

```

document summaries_gemma3_12b/

```
- High-level summaries of documents
- Used for:
  - Downstream reasoning
  - Holistic evaluation

---

## 🎥 Video Processing Agents

### Raw Video
```

video_interviews/

```

---

### Frame Extraction + Understanding

```

video_frame_text_gemma3_12b/
video_frame_text_gemma3_4b/

```
- Mid-frame extraction + captioning
- Different model sizes for experimentation

---

### Derived Modalities (global folders)

Outside individual application folders:

```

video_interviews_audio_files/
video_interviews_audio_transcriptions_text/
video_interviews_audio_emotions/
video_interviews_blendshape_files/
video_interviews_middle_frame_image/
video_interviews_transcriptions_grade_info/

```

These represent **pipeline stages shared across applications**:

| Folder | Description |
|------|--------|
| audio_files | Extracted audio (.mp3) |
| audio_transcriptions_text | Whisper transcripts |
| audio_emotions | Emotion features |
| blendshape_files | Face / motion features |
| middle_frame_image | Representative frame |
| transcriptions_grade_info | LLM-based evaluation |

---

## 🔁 Pipeline Philosophy

Each folder = **one agent output**

This enables:
- Full transparency
- Easy debugging
- Independent re-execution
- Notebook-level reproducibility

---

## 📦 Colab Output Root

```

colab-output/
├── dream_applicant/
├── dream_applicant_application/

```

- `dream_applicant_application/` → main working directory
- Contains all processed applications

---

## 🔄 Data Flow Summary

```

RAW INPUT
↓
documents_image / video_interviews
↓
OCR + LLM AGENTS
↓
STRUCTURED TEXT + FEATURES
↓
SUMMARIZATION / SCORING
↓
APPLICANT-LEVEL REASONING

```

---

## 🧩 Key Design Principles

- **One folder = one agent**
- **No hidden transformations**
- **Everything is file-based**
- **Compatible with Colab execution**
- **Direct mapping to enterprise services**

---

## 🚀 Future Extension

This structure can be automatically converted into:
- Microservices
- API pipelines
- Workflow orchestration systems

Each folder → becomes a service endpoint

---

## 📝 Notes

- Naming reflects **model + task**
- Multiple variants allow benchmarking
- Structure supports **auditability (EU AI Act readiness)**

```

---


