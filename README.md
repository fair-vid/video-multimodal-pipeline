# Video Multimodal Pipeline

A comprehensive toolkit for extracting and processing multimodal data from video files. This project provides Google Colab notebooks that transform raw video data into structured, analyzable formats including audio, text transcriptions, visual frames, and AI-generated descriptions.

## 🎯 Project Overview

This pipeline enables researchers, data scientists, and ML engineers to efficiently process video datasets by extracting multiple data modalities:

- **Audio tracks** (MP3 format)
- **Text transcriptions** (using OpenAI Whisper)
- **Video frames** (middle frame extraction)
- **Visual descriptions** (using Google Gemini/Gemma LLM)

All processing is done in Google Colab with outputs saved to Google Drive for easy access and further analysis.

## 📋 Table of Contents

- [Features](#features)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Usage](#usage)
- [Project Structure](#project-structure)
- [Notebooks](#notebooks)
- [Output Format](#output-format)
- [Future Development](#future-development)
- [Contributing](#contributing)
- [License](#license)

## ✨ Features

- **Zero local setup** - All processing runs in Google Colab
- **Multimodal extraction** - Audio, text, images, and descriptions from a single source
- **Scalable processing** - Batch processes entire video datasets
- **Cloud storage** - Automatic archiving to Google Drive
- **Modular pipeline** - Independent notebooks that work together
- **AI-powered descriptions** - Leverages Google's latest LLM models
- **Ready for ML** - Outputs structured data suitable for training models

## 🔧 Prerequisites

### Required:
- Google account (for Colab and Drive)
- Google Gemini API key ([Get one here](https://aistudio.google.com/app/apikey))
- Kaggle account (for dataset access)

### Recommended:
- Basic Python knowledge
- Familiarity with Google Colab
- Understanding of video/audio processing concepts

## 📦 Installation

No local installation required! Everything runs in Google Colab.

### Setup Steps:

1. **Clone this repository:**
   ```bash
   git clone https://github.com/yourusername/video-multimodal-pipeline.git
   ```

2. **Upload notebooks to Google Drive** or open directly from GitHub in Colab

3. **Configure API keys:**
   - Add your Google Gemini API key to Colab Secrets:
     - Click 🔑 icon in Colab sidebar
     - Add secret: Name = `GOOGLE_API_KEY`, Value = your API key

4. **You're ready to go!**

## 🚀 Usage

### Step 1: Extract Multimodal Data from Videos

Open `video_multimodal_extraction.ipynb` in Google Colab and run all cells.

**What it does:**
- Downloads video dataset from Kaggle
- Extracts audio tracks → `audio-data/`
- Transcribes audio to text → `text-data.zip`
- Captures middle frames → `frame-data.zip`
- Saves archives to Google Drive

**Runtime:** ~10-30 minutes depending on dataset size

### Step 2: Generate Image Descriptions

Open `image_description_generation.ipynb` in Google Colab and run all cells.

**What it does:**
- Loads extracted frames from Drive
- Processes each image with Gemini/Gemma LLM
- Generates natural language descriptions
- Archives descriptions → `image-descriptions.zip`

**Runtime:** ~5-15 minutes depending on number of images and model choice

### Outputs Location:

All outputs are saved to: `Google Drive/MyDrive/colab-output/`

## 📁 Project Structure

```
video-multimodal-pipeline/
│
├── notebooks/
│   ├── video_multimodal_extraction.ipynb    # Step 1: Extract audio, text, frames
│   └── image_description_generation.ipynb   # Step 2: Generate image descriptions
│
├── examples/
│   └── sample_outputs/                      # Example output files
│
├── docs/
│   ├── setup_guide.md                       # Detailed setup instructions
│   └── api_configuration.md                 # API key configuration guide
│
├── README.md                                 # This file
└── LICENSE                                   # License information
```

## 📓 Notebooks

### 1. video_multimodal_extraction.ipynb

**Purpose:** Initial video processing and multimodal data extraction

**Pipeline stages:**
1. Download dataset from Kaggle
2. Extract audio from videos (MoviePy)
3. Install Whisper for transcription
4. Transcribe audio to text
5. Extract middle frame from each video
6. Archive and save to Google Drive

**Input:** Video files (MP4)  
**Output:** `audio-data/`, `text-data.zip`, `frame-data.zip`

### 2. image_description_generation.ipynb

**Purpose:** AI-powered visual understanding and description generation

**Pipeline stages:**
1. Extract frames from archive
2. Process images with Gemini/Gemma LLM
3. Generate natural language descriptions
4. Archive descriptions to Drive

**Input:** `frame-data.zip`  
**Output:** `image-descriptions.zip`

**Supported models:**
- `gemini-1.5-flash` - Fast, efficient, recommended for most use cases
- `gemma-3-27b-it` - More detailed, powerful descriptions

## 📊 Output Format

### Audio Files
```
audio-data/
├── 1.mp3
├── 2.mp3
└── 3.mp3
```

### Text Transcriptions
```
text-data/
├── 1.txt          # "Hello, this is a video about..."
├── 2.txt
└── 3.txt
```

### Frame Images
```
frame-data/
├── 1.jpg          # Middle frame from video 1
├── 2.jpg
└── 3.jpg
```

### Image Descriptions
```
image-descriptions/
├── 1.txt          # "The image shows a person standing..."
├── 2.txt
└── 3.txt
```

## 🔮 Future Development

This is just the beginning! Planned enhancements include:

### Phase 2: Advanced Processing
- [ ] Emotion detection from audio (speech emotion recognition)
- [ ] Face detection and analysis in frames
- [ ] Sentiment analysis of transcriptions
- [ ] Multi-frame extraction (not just middle frame)

### Phase 3: Analysis & Insights
- [ ] Emotion timeline visualization
- [ ] Cross-modal emotion alignment (audio + visual + text)
- [ ] Speaker diarization
- [ ] Scene detection and segmentation

### Phase 4: ML Integration
- [ ] Dataset preparation for emotion recognition models
- [ ] Pre-built model training pipelines
- [ ] Inference notebooks for new videos
- [ ] Model evaluation and metrics

### Phase 5: Automation
- [ ] Batch processing scripts
- [ ] API endpoints for video processing
- [ ] Web interface for easy uploads
- [ ] Real-time processing support

## 🤝 Contributing

Contributions are welcome! Here's how you can help:

1. **Fork the repository**
2. **Create a feature branch** (`git checkout -b feature/AmazingFeature`)
3. **Commit your changes** (`git commit -m 'Add some AmazingFeature'`)
4. **Push to the branch** (`git push origin feature/AmazingFeature`)
5. **Open a Pull Request**

### Areas where we need help:
- Additional data modality extractors
- Performance optimization
- Documentation improvements
- Example notebooks for specific use cases
- Bug fixes and testing

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- [Kaggle](https://www.kaggle.com/) - For hosting the emotional video dataset
- [OpenAI Whisper](https://github.com/openai/whisper) - Speech recognition model
- [Google Gemini](https://deepmind.google/technologies/gemini/) - Multimodal AI model
- [MoviePy](https://zulko.github.io/moviepy/) - Video editing library

## 📧 Contact

For questions, suggestions, or collaboration opportunities:

- **GitHub Issues:** [Create an issue](https://github.com/yourusername/video-multimodal-pipeline/issues)
- **Email:** your.email@example.com
- **LinkedIn:** [Your Profile](https://linkedin.com/in/yourprofile)

---

**⭐ If you find this project useful, please consider giving it a star!**

---

### Quick Start Command

```bash
# Clone and get started in 3 commands
git clone https://github.com/yourusername/video-multimodal-pipeline.git
cd video-multimodal-pipeline
# Open notebooks/video_multimodal_extraction.ipynb in Google Colab
```
