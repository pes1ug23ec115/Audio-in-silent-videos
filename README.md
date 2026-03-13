# DL Project: Audio-in-Silent-Videos

This repository contains notebooks and experiment artifacts for building a video-audio pipeline using the VGGSound dataset.

The main workflow is centered on:
- dataset inspection and metadata generation,
- VGGSound video collection,
- audio extraction from video,
- frame extraction for visual features,
- training and loading audio/video encoder checkpoints.

## Repository Layout

- `dlproject.ipynb`: Main end-to-end notebook (data prep, preprocessing, model workflow).
- `test.ipynb`: Additional testing notebook.
- `ATTEMPT_1_600VIDS`: Experiment artifact marker for a 600-video run.
- `auto_push.bat`: Utility script for quick git push automation.
- `requirements.txt`: Python dependency list for local setup.
- `README.md`: Project documentation.

## What The Notebook Covers

Based on the current notebook flow, the pipeline includes:

1. VGGSound dataset exploration and metadata export (CSV/XLSX).
2. Video download and organization into local folders.
3. Audio extraction (WAV) from MP4 files.
4. Frame extraction from videos for visual processing.
5. Building/loading model checkpoints with PyTorch encoders.

## Environment

Recommended:
- Python 3.10+
- Jupyter Notebook or VS Code Notebook support
- FFmpeg installed and available in PATH

Typical Python packages used in the notebook:
- torch
- torchvision
- numpy
- pandas
- opencv-python
- librosa
- tqdm
- yt-dlp

Install dependencies:

```bash
pip install -r requirements.txt
```

## Quick Start

1. Open `dlproject.ipynb`.
2. Update dataset paths in cells (for example `VIDEO_DIR`, `AUDIO_DIR`, and any Google Drive paths).
3. Run cells in order from top to bottom.
4. Verify outputs:
   - downloaded videos,
   - extracted `.wav` files,
   - extracted frames,
   - checkpoint files (if training/loading is enabled).

## Notes On Paths

Some cells currently reference Colab-style paths such as:
- `/content/vggsound/videos`
- `/content/drive/MyDrive/...`

For local Windows execution, replace these with local absolute paths (for example `C:/Users/<username>/...`) before execution.

## Reproducibility Tips

- Keep dataset and output directories consistent across runs.
- Save generated metadata files per experiment.
- Store model checkpoints with run names (for example `best_model_attempt1.pth`).
- Log the number of processed videos/audio/frame folders after each stage.

## Current Status

This project is in active experimentation mode, with notebook-first development and iterative attempts (including a 600-video attempt).
