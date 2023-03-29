# Stable Diffusion WebUI Docker

Run Stable Diffusion on your machine with a nice UI without any hassle!

## Setup & Usage

Visit the wiki for [Setup](https://github.com/AbdBarho/stable-diffusion-webui-docker/wiki/Setup) and [Usage](https://github.com/AbdBarho/stable-diffusion-webui-docker/wiki/Usage) instructions, checkout the [FAQ](https://github.com/AbdBarho/stable-diffusion-webui-docker/wiki/FAQ) page if you face any problems, or create a new issue!

## Leon Setup and Usage !!!!!!

Please follow these [guide](#leon-guide) at the bottom section for the setups.

## Features

This repository provides multiple UIs for you to play around with stable diffusion:

### [AUTOMATIC1111](https://github.com/AUTOMATIC1111/stable-diffusion-webui)

[Full feature list here](https://github.com/AUTOMATIC1111/stable-diffusion-webui-feature-showcase), Screenshots:

| Text to image                                                                                              | Image to image                                                                                             | Extras                                                                                                     |
| ---------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------- |
| ![](https://user-images.githubusercontent.com/24505302/189541954-46afd772-d0c8-4005-874c-e2eca40c02f2.jpg) | ![](https://user-images.githubusercontent.com/24505302/189541956-5b528de7-1b5d-479f-a1db-d3f5a53afc59.jpg) | ![](https://user-images.githubusercontent.com/24505302/189541957-cf78b352-a071-486d-8889-f26952779a61.jpg) |

### [InvokeAI (lstein)](https://github.com/invoke-ai/InvokeAI)

[Full feature list here](https://github.com/invoke-ai/InvokeAI#features), Screenshots:

| Text to image                                                                                              | Image to image                                                                                             | Extras                                                                                                     |
| ---------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------- |
| ![](https://user-images.githubusercontent.com/24505302/195158552-39f58cb6-cfcc-4141-9995-a626e3760752.jpg) | ![](https://user-images.githubusercontent.com/24505302/195158553-152a0ab8-c0fd-4087-b121-4823bcd8d6b5.jpg) | ![](https://user-images.githubusercontent.com/24505302/195158548-e118206e-c519-4915-85d6-4c248eb10fc0.jpg) |

### [Sygil (sd-webui / hlky)](https://github.com/Sygil-Dev/sygil-webui)

[Full feature list here](https://github.com/Sygil-Dev/sygil-webui/blob/master/README.md), Screenshots:

| Text to image                                                                                              | Image to image                                                                                             | Image Lab                                                                                                  |
| ---------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------- |
| ![](https://user-images.githubusercontent.com/24505302/189541298-f902b021-a1eb-4e4b-b2eb-b6a696a8ec80.jpg) | ![](https://user-images.githubusercontent.com/24505302/189541295-7d7f2162-2189-4e0a-abbd-703f4779e1cd.jpg) | ![](https://user-images.githubusercontent.com/24505302/189541294-aa7f7735-a973-4e17-ada0-1fe3acbb1772.jpg) |

## Contributing

Contributions are welcome! **Create a discussion first of what the problem is and what you want to contribute (before you implement anything)**

## Disclaimer

The authors of this project are not responsible for any content generated using this interface.

This license of this software forbids you from sharing any content that violates any laws, produce any harm to a person, disseminate any personal information that would be meant for harm, spread misinformation and target vulnerable groups. For the full list of restrictions please read [the license](./LICENSE).

## Thanks

Special thanks to everyone behind these awesome projects, without them, none of this would have been possible:

- [AUTOMATIC1111/stable-diffusion-webui](https://github.com/AUTOMATIC1111/stable-diffusion-webui)
- [InvokeAI](https://github.com/invoke-ai/InvokeAI)
- [Sygil-webui](https://github.com/Sygil-Dev/sygil-webui)
- [CompVis/stable-diffusion](https://github.com/CompVis/stable-diffusion)
- and many many more.


## Leon guide

Install nvidia CUDA enabled docker.

https://docs.nvidia.com/datacenter/cloud-native/container-toolkit/install-guide.html


Run following steps

1. Download models
```
docker compose --profile download up --build
```

2. Run Stable Diffusion WebUI docker
```
docker compose --profile auto up --build

# or

./start.sh
```

3. Optionally add plugins for enable prompt for doll likeness.

```
khoya ss additional network
```


4. Example prompt
```
# kimono good
(8k, RAW photo, best quality, masterpiece:1.2), clear skin,big breast,(realistic, realistic body,photo-realistic:1.37), ultra-detailed,full body,fullbody,1 girl, solo,beautiful detailed sky,detailed Tokyo street,night,beautiful detailed eyes,beautiful detailed lips,professional lighting, photon mapping, radiosity, physically-based rendering,extremely detailed eyes and face, beautiful detailed eyes,light on face,cinematic lighting,full-body shot,looking at viewer,outdoors,(kimono :1.7)

# kimono neg
EasyNegative, paintings, sketches, (worst quality:2), (NSFW:2), (nipple:2),(low quality:2), (normal quality:2), lowres, ((monochrome)), ((grayscale)), skin spots, acnes, skin blemishes, age spot, glans,extra fingers,fewer fingers,strange fingers,bad hand,signature, watermark, username, blurry, bad feet,bad leg, duplicate, extra limb, ugly, disgusting, poorly drawn hands, missing limb, floating limbs, disconnected limbs, malformed hands, blurry,mutated hands and fingers,, EasyNegative, paintings, sketches, (worst quality:2), (low quality:2), (normal quality:2), lowres, ((monochrome)), ((grayscale)), skin spots, acnes, skin blemishes, age spot, glans,extra fingers,fewer fingers,strange fingers,bad hand,signature, watermark, username, blurry, bad feet,bad leg, (naked:2)

# settings
Sampling method: DPM++ SDE Keras
Sampling steps: 20 - 80


# additional network plugin enabled
# kimono good
(8k, RAW photo, best quality, masterpiece:1.2), <lora:Japanese-doll-likeness:0.2> <lora:Korean-doll-likeness:0.2>, clear skin,big breast,(realistic, realistic body,photo-realistic:1.37), ultra-detailed,full body,fullbody,1 girl, solo,beautiful detailed sky,detailed Tokyo street,night,beautiful detailed eyes,beautiful detailed lips,professional lighting, photon mapping, radiosity, physically-based rendering,extremely detailed eyes and face, beautiful detailed eyes,light on face,cinematic lighting,full-body shot,looking at viewer,outdoors,(kimono :1.7)

# kimono neg
EasyNegative, paintings, sketches, (worst quality:2), (NSFW:2), (nipple:2),(low quality:2), (normal quality:2), lowres, ((monochrome)), ((grayscale)), skin spots, acnes, skin blemishes, age spot, glans,extra fingers,fewer fingers,strange fingers,bad hand,signature, watermark, username, blurry, bad feet,bad leg, duplicate, extra limb, ugly, disgusting, poorly drawn hands, missing limb, floating limbs, disconnected limbs, malformed hands, blurry,mutated hands and fingers,, EasyNegative, paintings, sketches, (worst quality:2), (low quality:2), (normal quality:2), lowres, ((monochrome)), ((grayscale)), skin spots, acnes, skin blemishes, age spot, glans,extra fingers,fewer fingers,strange fingers,bad hand,signature, watermark, username, blurry, bad feet,bad leg, (naked:2)

```

5. How to operate
```
chinese tutorial

https://www.youtube.com/watch?v=OoTgK7w-gjQ&list=PLFh8u7KsoA52ZVfEjMjI8sLmDybToqczE&ab_channel=KasKuoLab
```