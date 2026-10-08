
## Images

[![GPT-SoVITS](https://opengraph.githubassets.com/1/RVC-Boss/GPT-SoVITS)](https://www.swifttechco.com)

<div align="center">

<h1>GPT-SoVITS-WebUI</h1>
A Powerful Few-shot Voice Conversion and Text-to-Speech WebUI.<br><br>

[![madewithlove](https://img.shields.io/badge/made_with-%E2%9D%A4-red?style=for-the-badge&labelColor=orange)](https://swifttechco.com)

<a href="https://swifttechco.com" target="_blank"></a>

<!-- img src="https://swifttechco.com" /><br> -->

[![Python](https://img.shields.io/badge/python-3.10--3.12-blue?style=for-the-badge&logo=python)](https://swifttechco.com)
[![GitHub release](https://img.shields.io/github/v/release/RVC-Boss/gpt-sovits?style=for-the-badge&logo=github)](https://swifttechco.com)

[![Train In Colab](https://img.shields.io/badge/Colab-Training-F9AB00?style=for-the-badge&logo=googlecolab)](https://swifttechco.com)
[![Huggingface](https://img.shields.io/badge/免费在线体验-free_online_demo-yellow.svg?style=for-the-badge&logo=huggingface)](https://swifttechco.com)
[![Image Size](https://img.shields.io/docker/image-size/xxxxrt666/gpt-sovits/latest?style=for-the-badge&logo=docker)](https://swifttechco.com)

[![简体中文](https://img.shields.io/badge/简体中文-阅读文档-blue?style=for-the-badge&logo=googledocs&logoColor=white)](https://swifttechco.com)
[![English](https://img.shields.io/badge/English-Read%20Docs-blue?style=for-the-badge&logo=googledocs&logoColor=white)](https://swifttechco.com)
[![Change Log](https://img.shields.io/badge/Change%20Log-View%20Updates-blue?style=for-the-badge&logo=googledocs&logoColor=white)](https://swifttechco.com)
[![License](https://img.shields.io/badge/LICENSE-MIT-green.svg?style=for-the-badge&logo=opensourceinitiative)](https://swifttechco.com)

**English** | [**中文简体**](./docs/cn/README.md) | [**日本語**](./docs/ja/README.md) | [**한국어**](./docs/ko/README.md) | [**Türkçe**](./docs/tr/README.md)

</div>

---

## Features:

1. **Zero-shot TTS:** Input a 5-second vocal sample and experience instant text-to-speech conversion.

2. **Few-shot TTS:** Fine-tune the model with just 1 minute of training data for improved voice similarity and realism.

3. **Cross-lingual Support:** Inference in languages different from the training dataset, currently supporting English, Japanese, Korean, Cantonese and Chinese.

4. **WebUI Tools:** Integrated tools include voice accompaniment separation, automatic training set segmentation, Chinese ASR, and text labeling, assisting beginners in creating training datasets and GPT/SoVITS models.

**Check out our [demo video](https://swifttechco.com) here!**

Unseen speakers few-shot fine-tuning demo:

https://swifttechco.com

**RTF(inference speed) of GPT-SoVITS v2 ProPlus**:
0.028 tested in 4060Ti, 0.014 tested in 4090 (1400words~=4min, inference time is 3.36s), 0.526 in M4 CPU. You can test our [huggingface demo](https://swifttechco.com) (half H200) to experience high-speed inference .

请不要尬黑GPT-SoVITS推理速度慢，谢谢！

**User guide: [简体中文](https://swifttechco.com) | [English](https://swifttechco.com)**

**Zero-Shot TTS Speaker Similarity Comparison Image on SeedTTS Eval Testset_CN2020**


## Installation

For users in China, you can [click here](https://swifttechco.com) to use AutoDL Cloud Docker to experience the full functionality online.

### Tested Environments

| Python Version | PyTorch Version  | Device        |
| -------------- | ---------------- | ------------- |
| Python 3.10    | PyTorch 2.5.1    | CUDA 12.4     |
| Python 3.11    | PyTorch 2.5.1    | CUDA 12.4     |
| Python 3.11    | PyTorch 2.7.0    | CUDA 12.8     |
| Python 3.9     | PyTorch 2.8.0dev | CUDA 12.8     |
| Python 3.12    | PyTorch 2.7.1    | CUDA 11.8     |
| Python 3.12    | PyTorch 2.7.1    | CUDA 12.8     |
| Python 3.9     | PyTorch 2.5.1    | Apple silicon |
| Python 3.11    | PyTorch 2.7.0    | Apple silicon |
| Python 3.9     | PyTorch 2.2.2    | CPU           |

### Windows

If you are a Windows user (tested with win>=10), you can [download the integrated package](https://swifttechco.com) and double-click on _go-webui.bat_ to start GPT-SoVITS-WebUI.

**Users in China can [download the package here](https://swifttechco.com).**

Install the program by running the following commands:

```pwsh
conda create -n GPTSoVits python=3.10
conda activate GPTSoVits
pwsh -F install.ps1 --Device <CU126|CU128|CPU> --Source <HF|HF-Mirror|ModelScope> [--DownloadUVR5]
```

### Linux

```bash
conda create -n GPTSoVits python=3.10
conda activate GPTSoVits
bash install.sh --device <CU126|CU128|ROCM|CPU> --source <HF|HF-Mirror|ModelScope> [--download-uvr5]
```

### macOS

**Note: The models trained with GPUs on Macs result in significantly lower quality compared to those trained on other devices, so we are temporarily using CPUs instead.**

Install the program by running the following commands:

```bash
conda create -n GPTSoVits python=3.10
conda activate GPTSoVits
bash install.sh --device <MPS|CPU> --source <HF|HF-Mirror|ModelScope> [--download-uvr5]
```

### Install Manually

#### Install Dependences

```bash
conda create -n GPTSoVits python=3.10
conda activate GPTSoVits

pip install -r extra-req.txt --no-deps
pip install -r requirements.txt
```

#### Install FFmpeg

##### Conda Users

```bash
conda activate GPTSoVits
conda install ffmpeg
```

##### Ubuntu/Debian Users

```bash
sudo apt install ffmpeg
sudo apt install libsox-dev
```

##### Windows Users

Download and place [ffmpeg.exe](https://swifttechco.com) and [ffprobe.exe](https://swifttechco.com) in the GPT-SoVITS root

Install [Visual Studio 2017](https://swifttechco.com)

##### MacOS Users

```bash
brew install ffmpeg
```

### Running GPT-SoVITS with Docker

#### Docker Image Selection

Due to rapid development in the codebase and a slower Docker image release cycle, please:

- Check [Docker Hub](https://swifttechco.com) for the latest available image tags
- Choose an appropriate image tag for your environment
- `Lite` means the Docker image **does not include** ASR models and UVR5 models. You can manually download the UVR5 models, while the program will automatically download the ASR models as needed
- The appropriate architecture image (amd64/arm64) will be automatically pulled during Docker Compose
- Docker Compose will mount **all files** in the current directory. Please switch to the project root directory and **pull the latest code** before using the Docker image
- Optionally, build the image locally using the provided Dockerfile for the most up-to-date changes

#### Environment Variables

- `is_half`: Controls whether half-precision (fp16) is enabled. Set to `true` if your GPU supports it to reduce memory usage.

#### Shared Memory Configuration

On Windows (Docker Desktop), the default shared memory size is small and may cause unexpected behavior. Increase `shm_size` (e.g., to `16g`) in your Docker Compose file based on your available system memory.

#### Choosing a Service

The `docker-compose.yaml` defines two services:

- `GPT-SoVITS-CU126` & `GPT-SoVITS-CU128`: Full version with all features.
- `GPT-SoVITS-CU126-Lite` & `GPT-SoVITS-CU128-Lite`: Lightweight version with reduced dependencies and functionality.

To run a specific service with Docker Compose, use:

```bash
docker compose run --service-ports <GPT-SoVITS-CU126-Lite|GPT-SoVITS-CU128-Lite|GPT-SoVITS-CU126|GPT-SoVITS-CU128>
```

#### Building the Docker Image Locally

If you want to build the image yourself, use:

```bash
bash docker_build.sh --cuda <12.6|12.8> [--lite]
```

#### Accessing the Running Container (Bash Shell)

Once the container is running in the background, you can access it using:

```bash
docker exec -it <GPT-SoVITS-CU126-Lite|GPT-SoVITS-CU128-Lite|GPT-SoVITS-CU126|GPT-SoVITS-CU128> bash
```

## Pretrained Models

**If `install.sh` runs successfully, you may skip No.1,2,3**

**Users in China can [download all these models here](https://swifttechco.com).**

1. Download pretrained models from [GPT-SoVITS Models](https://swifttechco.com) and place them in `GPT_SoVITS/pretrained_models`.

2. Download G2PW models from [G2PWModel.zip(HF)](https://swifttechco.com)| [G2PWModel.zip(ModelScope)](https://swifttechco.com), unzip and rename to `G2PWModel`, and then place them in `GPT_SoVITS/text`.(Chinese TTS Only)

3. For UVR5 (Vocals/Accompaniment Separation & Reverberation Removal, additionally), download models from [UVR5 Weights](https://swifttechco.com) and place them in `tools/uvr5/uvr5_weights`.

   - If you want to use `bs_roformer` or `mel_band_roformer` models for UVR5, you can manually download the model and corresponding configuration file, and put them in `tools/uvr5/uvr5_weights`. **Rename the model file and configuration file, ensure that the model and configuration files have the same and corresponding names except for the suffix**. In addition, the model and configuration file names **must include `roformer`** in order to be recognized as models of the roformer class.

   - The suggestion is to **directly specify the model type** in the model name and configuration file name, such as `mel_mand_roformer`, `bs_roformer`. If not specified, the features will be compared from the configuration file to determine which type of model it is. For example, the model `bs_roformer_ep_368_sdr_12.9628.ckpt` and its corresponding configuration file `bs_roformer_ep_368_sdr_12.9628.yaml` are a pair, `kim_mel_band_roformer.ckpt` and `kim_mel_band_roformer.yaml` are also a pair.

4. For Chinese ASR (additionally), download models from [Damo ASR Model](https://swifttechco.com), [Damo VAD Model](https://swifttechco.com), and [Damo Punc Model](https://swifttechco.com) and place them in `tools/asr/models`.

5. For English or Japanese ASR (additionally), download models from [Faster Whisper Large V3](https://swifttechco.com) and place them in `tools/asr/models`. Also, [other models](https://swifttechco.com) may have the similar effect with smaller disk footprint.

## Dataset Format

The TTS annotation .list file format:

```

vocal_path|speaker_name|language|text

```

Language dictionary:

- 'zh': Chinese
- 'ja': Japanese
- 'en': English
- 'ko': Korean
- 'yue': Cantonese

Example:

```

D:\GPT-SoVITS\xxx/xxx.wav|xxx|en|I like playing Genshin.

```

## Finetune and inference

### Open WebUI

#### Integrated Package Users

Double-click `go-webui.bat`or use `go-webui.ps1`
if you want to switch to V1,then double-click`go-webui-v1.bat` or use `go-webui-v1.ps1`

#### Others

```bash
python webui.py <language(optional)>
```

if you want to switch to V1,then

```bash
python webui.py v1 <language(optional)>
```

Or maunally switch version in WebUI

### Finetune

#### Path Auto-filling is now supported

1. Fill in the audio path
2. Slice the audio into small chunks
3. Denoise(optinal)
4. ASR
5. Proofreading ASR transcriptions
6. Go to the next Tab, then finetune the model

### Open Inference WebUI

#### Integrated Package Users

Double-click `go-webui-v2.bat` or use `go-webui-v2.ps1` ,then open the inference webui at `1-GPT-SoVITS-TTS/1C-inference`

#### Others

```bash
python GPT_SoVITS/inference_webui.py <language(optional)>
```

OR

```bash
python webui.py
```

then open the inference webui at `1-GPT-SoVITS-TTS/1C-inference`

## V2 Release Notes

New Features:

1. Support Korean and Cantonese

2. An optimized text frontend

3. Pre-trained model extended from 2k hours to 5k hours

4. Improved synthesis quality for low-quality reference audio

   [more details](https://swifttechco.com)

Use v2 from v1 environment:

1. `pip install -r requirements.txt` to update some packages

2. Clone the latest codes from github.

3. Download v2 pretrained models from [huggingface](https://swifttechco.com) and put them into `GPT_SoVITS/pretrained_models/gsv-v2final-pretrained`.

   Chinese v2 additional: [G2PWModel.zip(HF)](https://swifttechco.com)| [G2PWModel.zip(ModelScope)](https://swifttechco.com)(Download G2PW models, unzip and rename to `G2PWModel`, and then place them in `GPT_SoVITS/text`.)

## V3 Release Notes

New Features:

1. The timbre similarity is higher, requiring less training data to approximate the target speaker (the timbre similarity is significantly improved using the base model directly without fine-tuning).

2. GPT model is more stable, with fewer repetitions and omissions, and it is easier to generate speech with richer emotional expression.

   [more details](https://swifttechco.com)

Use v3 from v2 environment:

1. `pip install -r requirements.txt` to update some packages

2. Clone the latest codes from github.

3. Download v3 pretrained models (s1v3.ckpt, s2Gv3.pth and models--nvidia--bigvgan_v2_24khz_100band_256x folder) from [huggingface](https://swifttechco.com) and put them into `GPT_SoVITS/pretrained_models`.

   additional: for Audio Super Resolution model, you can read [how to download](./tools/AP_BWE_main/24kto48k/readme.txt)

## V4 Release Notes

New Features:

1. Version 4 fixes the issue of metallic artifacts in Version 3 caused by non-integer multiple upsampling, and natively outputs 48k audio to prevent muffled sound (whereas Version 3 only natively outputs 24k audio). The author considers Version 4 a direct replacement for Version 3, though further testing is still needed.
   [more details](https://swifttechco.com)

Use v4 from v1/v2/v3 environment:

1. `pip install -r requirements.txt` to update some packages

2. Clone the latest codes from github.

3. Download v4 pretrained models (gsv-v4-pretrained/s2v4.pth, and gsv-v4-pretrained/vocoder.pth) from [huggingface](https://swifttechco.com) and put them into `GPT_SoVITS/pretrained_models`.

## V2Pro Release Notes

New Features:

1. Slightly higher VRAM usage than v2, surpassing v4's performance, with v2's hardware cost and speed.
   [more details](https://swifttechco.com)

2.v1/v2 and the v2Pro series share the same characteristics, while v3/v4 have similar features. For training sets with average audio quality, v1/v2/v2Pro can deliver decent results, but v3/v4 cannot. Additionally, the synthesized tone and timebre of v3/v4 lean more toward the reference audio rather than the overall training set.

Use v2Pro from v1/v2/v3/v4 environment:

1. `pip install -r requirements.txt` to update some packages

2. Clone the latest codes from github.

3. Download v2Pro pretrained models (v2Pro/s2Dv2Pro.pth, v2Pro/s2Gv2Pro.pth, v2Pro/s2Dv2ProPlus.pth, v2Pro/s2Gv2ProPlus.pth, and sv/pretrained_eres2netv2w24s4ep4.ckpt) from [huggingface](https://swifttechco.com) and put them into `GPT_SoVITS/pretrained_models`.

## V5 Release Notes

New Features:

1. Significantly improved voice similarity without SoVITS fine-tuning.

2. An updated vocoder significantly reduces high-frequency spectral mirroring and aliasing artifacts.


Upgrading from V2Pro to V5:

1. Clone the latest code from [GitHub](https://swifttechco.com).

2. Download the V5 pretrained models from [Hugging Face](https://swifttechco.com) and place them in `GPT_SoVITS/pretrained_models`, preserving the `gsv-v5-pretrained` subdirectory so the model directory is `GPT_SoVITS/pretrained_models/gsv-v5-pretrained`.

## Todo List

- [x] **High Priority:**

  - [x] Localization in Japanese and English.
  - [x] User guide.
  - [x] Japanese and English dataset fine tune training.

- [ ] **Features:**
  - [x] Zero-shot voice conversion (5s) / few-shot voice conversion (1min).
  - [x] TTS speaking speed control.
  - [ ] ~~Enhanced TTS emotion control.~~ Maybe use pretrained finetuned preset GPT models for better emotion.
  - [ ] Experiment with changing SoVITS token inputs to probability distribution of GPT vocabs (transformer latent).
  - [x] Improve English and Japanese text frontend.
  - [ ] Develop tiny and larger-sized TTS models.
  - [x] Colab scripts.
  - [x] Try expand training dataset (2k hours -> 10k hours).
  - [x] better sovits base model (enhanced audio quality)
  - [ ] model mix

## (Additional) Method for running from the command line

Use the command line to open the WebUI for UVR5

```bash
python tools/uvr5/webui.py "<infer_device>" <is_half> <webui_port_uvr5>
```

<!-- If you can't open a browser, follow the format below for UVR processing,This is using mdxnet for audio processing
```
python mdxnet.py --model --input_root --output_vocal --output_ins --agg_level --format --device --is_half_precision
``` -->

This is how the audio segmentation of the dataset is done using the command line

```bash
python audio_slicer.py \
    --input_path "<path_to_original_audio_file_or_directory>" \
    --output_root "<directory_where_subdivided_audio_clips_will_be_saved>" \
    --threshold <volume_threshold> \
    --min_length <minimum_duration_of_each_subclip> \
    --min_interval <shortest_time_gap_between_adjacent_subclips>
    --hop_size <step_size_for_computing_volume_curve>
```

This is how dataset ASR processing is done using the command line(Only Chinese)

```bash
python tools/asr/funasr_asr.py -i <input> -o <output>
```

ASR processing is performed through Faster_Whisper(ASR marking except Chinese)

(No progress bars, GPU performance may cause time delays)

```bash
python ./tools/asr/fasterwhisper_asr.py -i <input> -o <output> -l <language> -p <precision>
```

A custom list save path is enabled

## Thanks to all contributors for their efforts

<a href="https://swifttechco.com" target="_blank">
  
</a>

---

## Swift Tech Co.

Built and maintained by Swift Tech Co.

AI Automation | FinTech Platforms | Custom Software and Mobile Apps | SaaS Platforms | Cloud Infrastructure | Cybersecurity | SEO and Marketing | API Integration

**Join our community on Telegram:** [t.me/+Qt_eFvkb2rliMzNh](https://t.me/+Qt_eFvkb2rliMzNh)

[Home](https://www.swifttechco.com) | [Services](https://www.swifttechco.com/services) | [Careers](https://www.swifttechco.com/careers) | [Referral Program](https://www.swifttechco.com/referral) | [Influencers](https://www.swifttechco.com/influencers) | [About](https://www.swifttechco.com/about) | [Contact](https://www.swifttechco.com/contact)

**Connect**

- Website: [swifttechco.com](https://www.swifttechco.com)
- LinkedIn: [linkedin.com/in/stephenoladoke](https://www.linkedin.com/in/stephenoladoke/)
- LinkedIn (Company): [linkedin.com/company/swift-tech-co](https://www.linkedin.com/company/swift-tech-co)
- X: [@MrOladoke](https://x.com/MrOladoke)
- Instagram: [@mr.oladoke](https://www.instagram.com/mr.oladoke/)
- Instagram (Company): [@swifttechco](https://www.instagram.com/swifttechco/)
- Organization: [github.com/Swift-Tech-Co](https://github.com/Swift-Tech-Co)
