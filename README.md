# LIP-SYNC
## MuseTalk

MuseTalk: Real-Time High Quality Lip Synchronization with Latent Space Inpainting
**Drive** link : https://drive.google.com/drive/folders/1GyP__si2oQveB7Ehfyjwabph3DUUc47g?usp=sharing




### Reference
-  **MuseTalk** :https://github.com/TMElyralab/MuseTalk/tree/main?tab=readme-ov-file
-  **MuseV**    : https://github.com/TMElyralab/MuseV/tree/main


### Download weights
You can download weights manually as follows:

Download our trained weights.

Download the weights of other components:

sd-vae-ft-mse
whisper
dwpose
face-parse-bisent
resnet18
Finally, these weights should be organized in models as follows:

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
