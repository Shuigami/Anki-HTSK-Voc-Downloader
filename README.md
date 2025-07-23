# Anki HTSK Vocabulary Downloader

This project automates the process of downloading Korean vocabulary audio files from HowToStudyKorean.com, transcribing them using OpenAI Whisper, and updating Anki cards via AnkiConnect.

## Features

- Asynchronous download of MP3 files for HTSK Unit 2 lessons
- Automatic filename formatting and duplicate handling
- Transcription of audio files using HuggingFace Transformers (Whisper model)
- CSV export of vocabulary and transcriptions
- Integration with Anki via AnkiConnect to update card audio fields

## Installation

1. **Install [uv](https://github.com/astral-sh/uv):**
   ```zsh
   pip install uv
   ```

2. **Install dependencies:**
   ```zsh
   uv pip install -r requirements.txt
   ```

## Usage

### 1. Download Vocabulary Audio

Run the downloader script to fetch MP3 files and generate `vocabulary.csv`:
```zsh
uv run python downloader.py
```

### 2. Transcribe Audio Files

Transcribe all downloaded audio files and save results to `transcriptions.csv`:
```zsh
uv run python huggingface.py
```

### 3. Update Anki Cards

Make sure Anki is running and AnkiConnect is installed. Then update your deck:
```zsh
uv run python update_anki.py
```

## Configuration

- Audio files are saved in the `audios/` directory, organized by lesson.
- CSV files (`vocabulary.csv`, `transcriptions.csv`) are generated in the project root.
- The Anki deck name is set to `Korean::HTSK Vocab - Unit 2` (edit in `update_anki.py` if needed).

## Requirements

- Python 3.12+
- Anki with [AnkiConnect](https://ankiweb.net/shared/info/2055492159) installed and running
- [uv](https://github.com/astral-sh/uv) for fast dependency management
