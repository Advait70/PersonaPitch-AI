# PersonaPitch AI

**AI-powered system to transform songs and speech into a different voice, using deep learning-based voice conversion and remixing.**

---

## Project Overview
PersonaPitch AI is an advanced deep learning pipeline that:
- **Separates** vocals and instrumentals from songs.
- **Converts** vocals into a target voice using StarGAN-v2 with a ParallelWaveGAN vocoder.
- **Cleans** vocals with optional noise reduction and EQ.
- **Remixes** vocals and instrumental together to create a polished final track.

The system is built for creative voice transformation and runs fully on a single GPU.

---

## Repository Structure
```
PersonaPitch_AI/
├── Configs/             # Configuration files for training and inference
├── Demo/                # Example reference voices and audio files
├── separated/           # Separated vocals and instrumentals (Demucs output)
├── main.py              # Main script for inference and voice conversion
└── README.md            # Project documentation
```
Dataset link: https://datashare.ed.ac.uk/handle/10283/3443
The pretrained StarGANv2 and ParallelWaveGAN on VCTK corpus can be downloaded at [StarGANv2 Link](https://huggingface.co/yl4579/StarGANv2-VC/blob/main/Models.zip) and [ParallelWaveGAN Link](https://huggingface.co/yl4579/StarGANv2-VC/blob/main/Vocoder.zip). Please unzip to `Models` and `Vocoder` respectivey and run each cell in the notebook.
---

## How to Use

1. **Install dependencies manually** (e.g., `torch`, `torchaudio`, `librosa`, `noisereduce`).
2. **Prepare inputs**:
   - Isolated `vocals.wav` and `no_vocals.wav` from any song.
   - A reference voice clip for conversion.
3. **Run the main pipeline**:
    main.py
4. Output will be generated as a fully remixed track.

---

## File Descriptions

- `Configs/`: YAML configuration files for model settings and fine-tuning parameters.
- `Demo/`: Folder for sample inputs like reference audios.
- `separated/`: Contains separated vocals and instrumental tracks.
- `main.py`: Single entry point to perform voice conversion and remixing.
- `README.md`: Documentation for understanding and using the project.

---

## Technologies Used
- **Deep Learning / AI**: PyTorch, GAN-based voice conversion (StarGAN-v2)
- **Voice Processing**: ParallelWaveGAN, Demucs
- **Audio Processing**: torchaudio, librosa, noisereduce
- **GPU Acceleration**: CUDA