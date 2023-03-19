# About

Pre-configured Google Colab notebooks to run [AUTOMATIC1111/stable-diffusion-webui](https://github.com/AUTOMATIC1111/stable-diffusion-webui) based on [camenduru/stable-diffusion-webui-colab](https://github.com/camenduru/stable-diffusion-webui-colab). 

## Versions

| Colab | Version | Description |
| --- | --- | --- |
| [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/datamonet/sd-webui-colab/blob/main/sd_webui_standard.ipynb)| Standard | Basic WebUI with extensions listed below. Standard version takes about 5 minutes to setup |
| [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/datamonet/sd-webui-colab/blob/main/sd_webui_controlnet.ipynb)| ControlNet | Standard + ControlNet extensions and models, which takes 1 or 2 minutes more than the standard version to setup given additional ControlNet models to download |

Click one of the two buttons above to run the Colab Notebook:

<img width="450" src="https://user-images.githubusercontent.com/595772/226143659-07f31032-e4ec-4e1a-92a6-0aeb60e1f3e7.png">

Click "Run anyway" in the warning window:

<img width="450" src="https://user-images.githubusercontent.com/595772/226143733-834ace15-0708-42d4-8029-7f4e6da53ad0.png">

After a few minutes, you should see the following messages in Colab. Click the public link to access WebUI in a new browser window or tab:

<img width="450" src="https://user-images.githubusercontent.com/595772/226143944-45c672cc-0b50-490e-ab07-6dcb2fefccf9.png">

## Extensions

The following extensions are pre-configured for all versions.

- https://github.com/AlUlkesh/stable-diffusion-webui-images-browser
- https://github.com/kohya-ss/sd-webui-additional-networks
- https://github.com/etherealxx/batchlinks-webui

The following are additional extensions for ControlNet version.

- https://github.com/Mikubill/sd-webui-controlnet
- https://github.com/camenduru/openpose-editor
- https://github.com/jexom/sd-webui-depth-lib
- https://github.com/hnmr293/posex


## Models

Only Stable Diffusion v1.5 model is pre-configured: [v1-5-pruned-emaonly.safetensors](https://huggingface.co/runwayml/stable-diffusion-v1-5/resolve/main/v1-5-pruned-emaonly.safetensors) from [runwayml/stable-diffusion-v1-5](https://huggingface.co/runwayml/stable-diffusion-v1-5)

You can use pre-installed [batchlinks-webui](https://github.com/etherealxx/batchlinks-webui) extension to easily install additional models (checkpoint, lora, embedding, vae, etc.) of your choice.

<img width="1101" alt="Screenshot 2023-03-18 at 6 46 53 PM" src="https://user-images.githubusercontent.com/595772/226144004-bf2802c2-ef14-48f4-b988-d2021be986b9.png">

As an exmaple, we show below how you can get one checkpoint from Huggingface and one lora model from CivitAI - please refer to the official [README](https://github.com/etherealxx/batchlinks-webui) to learn how to get model links from other sources and other functions.

The link for the checkpoint "ChilloutMix" on Huggingface is [https://huggingface.co/datamonet/ChilloutMix/tree/main](https://huggingface.co/datamonet/ChilloutMix/tree/main).

**Right click** the model you want to get and choose **Copy Link Address**:

<img width="800" src="https://user-images.githubusercontent.com/595772/226144297-f038a0fd-7a98-4d49-8e7e-7b252732b0b6.png">

The link for the lora on CivitAI is [https://civitai.com/models/12597/moxin](https://civitai.com/models/12597/moxin) - **NOTE**: this is **NOT** the link for the model.

**Right click** the Download Latest button and choose **Copy Link Address**:

<img width="800" src="https://user-images.githubusercontent.com/595772/226144430-a5e41313-da26-490a-9883-fa40f04faf80.png">

If the model has multiple versions, you can scroll down to get the address in the same way:

<img width="800" src="https://user-images.githubusercontent.com/595772/226144508-a94c3aec-ce96-439d-a68a-dedf4f1286c1.png">

Now, you can put the following text to [batchlinks-webui](https://github.com/etherealxx/batchlinks-webui) extension:

```
#model
https://huggingface.co/datamonet/ChilloutMix/resolve/main/chilloutmix_NiPrunedFp16.safetensors
#lora
https://civitai.com/api/download/models/14856
```

Or you can save the text into a `txt` file and load it in:

<img width="800" src="https://user-images.githubusercontent.com/595772/226144691-c368a966-c28b-4692-9f51-511faf92408a.png">

Then, click Download ALL button to download the models. 

You can switch to Colab to check the downloading progress:

<img width="600" src="https://user-images.githubusercontent.com/595772/226144846-9370a508-ae1c-430e-b7d5-0bd7e23c562f.png">

<img width="600" src="https://user-images.githubusercontent.com/595772/226144850-9de78267-e4d6-4d88-9ca2-f38dbc8d745b.png">

Now, you should have the `ChilloutMix` base model and `MoXin` lora:

<img width="1024" src="https://user-images.githubusercontent.com/595772/226146379-a43051f1-f87e-4c68-a06e-ae731c98430b.png">

You can replicate the image below by using the following prompt:

```
portrait of a woman standing , willow branches, (masterpiece, best quality:1.2), traditional chinese ink painting, modelshoot style, peaceful, (smile), looking at viewer, wearing long hanfu, hanfu, song, willow tree in background <lora:Moxin_10:0.8>
Negative prompt: (worst quality:2), (low quality:2), (normal quality:2), lowres, normal quality, skin spots, acnes, skin blemishes, age spot, glans, (watermark:2), hands
Steps: 30, Sampler: DPM++ SDE Karras, CFG scale: 3.5, Seed: 932584919, Size: 640x1024, Model hash: 1db9eb3bc3, Model: chilloutmix_NiPrunedFp16
```

<img width="400" src="https://user-images.githubusercontent.com/595772/226147118-cc234b16-e08b-47bc-97fb-5d7c0d4b95a8.png">
