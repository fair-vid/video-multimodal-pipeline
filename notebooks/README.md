# Notebooks

This directory contains links to the interactive Google Colab notebooks for the Video Multimodal Pipeline.

## 📓 Available Notebooks

### 1. Video Multimodal Extraction

Extract audio, text transcriptions, and frames from video files.

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1P1oWHEfyRYKXRvroefokW6-71tSHC4Ng#scrollTo=ZmKi09wMJGvC)

**Notebook:** [Demo_video_multimodal_extraction](https://colab.research.google.com/drive/1P1oWHEfyRYKXRvroefokW6-71tSHC4Ng#scrollTo=ZmKi09wMJGvC)

**What it does:**
- Downloads video dataset from Kaggle
- Extracts audio tracks (MP3)
- Transcribes audio to text using Whisper
- Captures middle frames from videos
- Saves all outputs to Google Drive

**Runtime:** ~10-30 minutes

---

### 2. Image Description Generation

Generate AI-powered descriptions for extracted video frames.

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/15r2XMoSW-xx3WPewuuZK3zUkfzGJBMF4#scrollTo=pj9ZsJPbZXwv)

**Notebook:** [Demo_image_description_generation](https://colab.research.google.com/drive/15r2XMoSW-xx3WPewuuZK3zUkfzGJBMF4#scrollTo=pj9ZsJPbZXwv)

**What it does:**
- Loads extracted frames from Google Drive
- Processes images with Gemini/Gemma LLM
- Generates natural language descriptions
- Archives descriptions to Drive

**Runtime:** ~5-15 minutes

---

## 🚀 How to Use

1. **Click the "Open in Colab" badge** above for the notebook you want to run
2. **Make a copy** to your own Google Drive (File → Save a copy in Drive)
3. **Configure your API keys** in Colab Secrets (🔑 icon in sidebar)
4. **Run all cells** (Runtime → Run all)
5. **Access outputs** in your Google Drive under `MyDrive/colab-output/`

## 📋 Prerequisites

- Google account
- Google Gemini API key ([Get one here](https://aistudio.google.com/app/apikey))
- Kaggle account (for Step 1 only)

## 💡 Tips

- Run notebooks in order: Step 1 → Step 2
- Each notebook can run independently after initial setup
- Outputs are automatically saved to your Google Drive
- You can modify the code in your copy to experiment

## ⚠️ Important Notes

- These are **shared view-only links**. Make a copy to edit and run.
- Ensure you have sufficient Google Drive storage (~1-5GB depending on dataset)
- API costs may apply when using Gemini/Gemma models

---

**Questions or issues?** [Open an issue](https://github.com/yourusername/video-multimodal-pipeline/issues) in the main repository.
