# LIP-SYNC
## MuseTalk

MuseTalk: Real-Time High Quality Lip Synchronization with Latent Space Inpainting
**Drive** link : https://drive.google.com/drive/folders/1GyP__si2oQveB7Ehfyjwabph3DUUc47g?usp=sharing




### Download weights
You can download weights manually as follows:

1. Download our trained [weights](https://huggingface.co/TMElyralab/MuseTalk).

2. Download the weights of other components:
   - [sd-vae-ft-mse](https://huggingface.co/stabilityai/sd-vae-ft-mse)
   - [whisper](https://openaipublic.azureedge.net/main/whisper/models/65147644a518d12f04e32d6f3b26facc3f8dd46e5390956a9424a650c0ce22b9/tiny.pt)
   - [dwpose](https://huggingface.co/yzd-v/DWPose/tree/main)
   - [face-parse-bisent](https://github.com/zllrunning/face-parsing.PyTorch)
   - [resnet18](https://download.pytorch.org/models/resnet18-5c106cde.pth)


Finally, these weights should be organized in `models` as follows:
```
./models/
├── musetalk
│   └── musetalk.json
│   └── pytorch_model.bin
├── dwpose
│   └── dw-ll_ucoco_384.pth
├── face-parse-bisent
│   ├── 79999_iter.pth
│   └── resnet18-5c106cde.pth
├── sd-vae-ft-mse
│   ├── config.json
│   └── diffusion_pytorch_model.bin
└── whisper
    └── tiny.pt
```
# Lip-Syncing Audio to Video

## Objective
To develop a pipeline that accurately lip-syncs provided audios to a given video, achieving a quality similar to the referenced video [13_K.mp4](link-to-video).

## Resources Provided
- Reference video: [13_K.mp4](link-to-video)
- Reference audio: [audio_folder](link-to-audio-folder)

## Deliverables
1. A detailed report explaining the methodology and models used.
2. Source code for the lip-syncing pipeline.
3. A generated video with synchronized lip-syncing using the provided audio.

## Tasks

### Task 1: Understand the Reference Video and Audio
- Analyzed the provided video [13_K.mp4](link-to-video) and the provided audio files.
- Identified the key components involved in lip-syncing.

### Task 2: Lip Syncing Model
- Selected an open-source lip-syncing model, specifically MuseTalk.
- Implemented the pipeline step-by-step in Colab, covering:
  - Environment setup
  - Configuration
  - Downloading weights and models
  - Inference and real-time inference
  - Adjusting parameters for better results
- Generated a high-quality video with excellent synchronization of lip movements with the audio.

### Task 3: Evaluation and Fine-Tuning
**Evaluation:**
- Compared the generated video with the reference video [13_K.mp4](link-to-video).
- Verified that the model provided good synchronization and overall video quality.

**Fine-Tuning:**
- Instead of fine-tuning the model, adjusted parameters like `bbox_shift` to control mouth openness, resulting in better synchronization.

## Results
- Generated a high-quality video with excellent synchronization of lip movements with the audio.

## Source Code
- The lip-syncing pipeline was implemented in a Colab notebook.
- All related materials, including the source code, are available on GitHub.

## Installation and Setup
1. Clone the repository:
    ```sh
    git clone https://github.com/your-repo/lip-syncing-pipeline.git
    cd lip-syncing-pipeline
    ```

2. Install the required packages:
    ```sh
    pip install --no-cache-dir -U openmim 
    mim install mmengine 
    mim install "mmcv>=2.0.1" 
    mim install "mmdet>=3.1.0" 
    mim install "mmpose>=1.1.0"  
    ```

## Usage
1. Set up the environment in Colab and upload the necessary files (models, videos, audios).
2. Update the configuration files as needed.
3. Run the inference script:
    ```sh
    python -m scripts.inference --inference_config configs/inference/test.yaml
    ```
4. For real-time inference:
    ```sh
    python -m scripts.realtime_inference --inference_config configs/inference/realtime.yaml --batch_size 4
    ```

## Detailed Report
A detailed report explaining the methodology and models used is included in the repository.

## Generated Video
The generated video with synchronized lip-syncing using the provided audio is available in the repository.

## Submission
Submit a zipped folder containing:
- The detailed report (PDF or Word document).
- Source code files.
- Generated video file.
- README file with instructions on how to run the code.

## Deadline
The deadline for this assignment is 5 days starting from the day you receive this assignment.

---

For more details, refer to the documentation provided in the repository. If you encounter any issues or have questions, feel free to open an issue or contact the maintainer.





### Reference
-  **MuseTalk** :https://github.com/TMElyralab/MuseTalk/tree/main?tab=readme-ov-file
-  **MuseV**    : https://github.com/TMElyralab/MuseV/tree/main

