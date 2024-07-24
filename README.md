# LIP-SYNC

## MuseTalk

### Overview
`MuseTalk` is a real-time high-quality audio-driven lip-syncing model trained in the latent space of `ft-mse-vae`, which

1. modifies an unseen face according to the input audio, with a size of face region of `256 x 256`.
1. Support audio in various languages, such as Chinese, English, and Japanese.
1. supports real-time inference with 30fps+ on an NVIDIA Tesla V100.
1. supports modification of the center point of the face region proposes, which **SIGNIFICANTLY** affects generation results. 
1. checkpoint available trained on the HDTF dataset.
   
[MuseTalk-Doc](https://github.com/TMElyralab/MuseTalk)

### Getting Started
We provide a detailed tutorial about the installation and the basic usage of MuseTalk for new users:

**The pipeline was implemented step-by-step in [Colab]([url](https://github.com/MohamedAziz15/Lip-Sync/blob/main/MuseTalk.ipynb)), covering all aspects including installation, configuration, downloading weights and models, performing inference, and real-time inference. Everything needed for the process was included**



#### 1. Download weights
You can copy the directory ("/content/drive/MyDrive/Lip-Sync/MuseTalk/musetalk/models") from [my drive](url) to your drive in the same path to work

**OR**

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


### Resources Provided
- Reference video: [13_K.mp4]([link-to-video](https://github.com/MohamedAziz15/Lip-Sync/blob/main/Resources/Video/13_K.mp4))
- Reference audio: [audio_folder]([link-to-audio-folder](https://github.com/MohamedAziz15/Lip-Sync/tree/main/Resources/Audio%20files))


###  Lip Syncing Model
- Selected an open-source lip-syncing model, specifically MuseTalk.
- Implemented the pipeline step-by-step in Colab, covering:
  - Environment setup
  - Configuration
  - Downloading weights and models
  - Inference and real-time inference
  - Adjusting parameters for better results
- Generated a high-quality video with excellent synchronization of lip movements with the audio.

**Evaluation:**
Compared the generated video with the reference video [13_K.mp4].
Verified that the model provided good synchronization and overall video quality.
Fine-Tuning:


**Fine-Tuning:**
 Instead of fine-tuning the model, adjusted parameters like bbox_shift to control mouth openness, resulting in better synchronization.

```
!python -m scripts.inference --inference_config configs/inference/test.yaml --bbox_shift -7
```

## Results
- Generated a high-quality video with excellent synchronization of lip movements with the audio.
[Inference](https://github.com/MohamedAziz15/Lip-Sync/tree/main/Generated-%20Inference)
 
[Real-Inference](https://github.com/MohamedAziz15/Lip-Sync/tree/main/Generated-Real-Inference) 



---


### Reference
-  **MuseTalk** :https://github.com/TMElyralab/MuseTalk/tree/main?tab=readme-ov-file
-  **MuseV**    : https://github.com/TMElyralab/MuseV/tree/main

For more details, refer to the documentation provided in the repository. If you encounter any issues or have questions, feel free to open an issue or contact the maintainer.



