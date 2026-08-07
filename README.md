<a id="top"></a>
<div align="center">

<h1>🎧 Awesome Continuous Audio VAE</h1>

<p><strong>A curated catalog of continuous audio VAEs and autoencoders for audio, music, singing, and speech.</strong></p>

<p>
<img src="https://img.shields.io/badge/models-56-4c78a8?style=flat-square" alt="56 models">
<img src="https://img.shields.io/badge/with_weights-38-2ca02c?style=flat-square" alt="38 with weights">
<img src="https://img.shields.io/badge/updated-2026--08--07-6f42c1?style=flat-square" alt="Updated 2026-08-07">
</p>

<p><a href="#audio">Audio / Sound</a> · <a href="#music">Music</a> · <a href="#singing">Singing</a> · <a href="#speech">Speech</a></p>

</div>

Papers, official implementations, pretrained weights, latent frame rates, dimensions, encoder/decoder architectures, and model I/O in one place.

## How to read the tables

- **Year–Month**: first public month (`YYYY-MM`); arXiv v1 for paper-backed entries, otherwise the official code or checkpoint release.
- **Sample rate**: native encoder rate used by the released model or its mel frontend.
- **Frame rate**: latent time steps produced per second of input audio.
- **Dim**: final latent width at each time step; 2-D mel latents are flattened across channel and frequency.
- **Input / Output**: the encoder input representation and the decoded output path.
- **Architecture**: coarse backbone family; **Encoder / Decoder** gives the concrete implementation.
- **Weights**: 🟢 standalone component · 🟡 bundled in a larger checkpoint · ⚪ unavailable.
- **N/R**: not reported in the linked paper, code, or checkpoint configuration.

<a id="audio"></a>
## 🔊 Audio / Sound

General audio, environmental sound, Foley, and multi-domain reconstruction. **25 models · 16 with weights.**

**Specifications**

| Model | Year–Month | Sample rate | Frame rate | Dim | Input | Output |
| --- | ---: | ---: | ---: | ---: | --- | --- |
| **OmniVAE audio-only** | 2026-07 | 48 kHz | 50 Hz | 128 | waveform | waveform |
| **Qwen-Audio-3 Shared VAE** | 2026-07 | 48 kHz | 25 Hz | 128 | stereo waveform | stereo waveform |
| **Qwen-Audio-VAE** | 2026-07 | 24 kHz | 12.5 Hz | 128 | waveform | waveform |
| **AudioCALM Audio VAE** | 2026-06 | 44.1 kHz | ≈10.75 Hz | 64 | stereo waveform | 44.1 kHz stereo waveform (iSTFT) |
| **KVAE-Audio** | 2026-06 | 48 kHz | 50 Hz | 64 | waveform | waveform |
| **STAR-VAE** | 2026-06 | N/R | N/R | N/R | waveform | waveform |
| **UniSonate Mel-VAE** | 2026-04 | 44.1 kHz | 43 Hz | 40 | mel spectrogram | decoded mel → vocoder → audio |
| **GenAE** | 2026-02 | 44.1 kHz | 13.125 Hz | N/R | multichannel waveform | multichannel waveform |
| **Ming-omni-tts continuous tokenizer** | 2026-02 | 44.1 kHz | 12.5 Hz | 64 | waveform | waveform |
| **LTX-2 Audio VAE** | 2026-01 | 16 kHz | 25 Hz | 128 | mel spectrogram | decoded mel → stereo vocoder → 24 kHz stereo waveform |
| **Omni2Sound OOB/Wav VAE** | 2026-01 | 16 kHz | 25 Hz | 64 | waveform | waveform |
| **HunyuanVideo-Foley Audio VAE** | 2025-08 | 48 kHz | 50 Hz | 128 | waveform | waveform |
| **Kling-Foley Mel-VAE** | 2025-06 | 44.1 kHz | 43 Hz | 40 | mel spectrogram | decoded mel → vocoder → audio |
| **MMAudio VAE 16 kHz** | 2024-12 | 16 kHz | 31.25 Hz | 20 | mel spectrogram | decoded mel → BigVGAN → audio |
| **MMAudio VAE 44.1 kHz** | 2024-12 | 44.1 kHz | 43.07 Hz | 40 | mel spectrogram | decoded mel → BigVGAN → audio |
| **MultiFoley DAC-VAE** | 2024-11 | 48 kHz | 40 Hz | 64 | waveform | waveform |
| **DACVAE / Movie Gen Audio Autoencoder** | 2024-10 | 48 kHz | 25 Hz | 128 | waveform | waveform |
| **EzAudio 1-D VAE** | 2024-09 | 24 kHz | 50 Hz | 128 | waveform | waveform |
| **StableAudio1.0 / Stable Audio Open VAE** | 2024-07 | 44.1 kHz | 21.5 Hz | 64 | waveform | waveform |
| **Wave-VAE (Stability AI)** | 2024-07 | 44.1 kHz | 21 Hz | 64 | waveform | waveform |
| **Auffusion VAE** | 2024-01 | 16 kHz | 12.5 Hz | 128 | mel-spectrogram image | decoded mel → HiFi-GAN → audio |
| **AudioLDM 2 VAE** | 2023-08 | 16 kHz | 25 Hz | 128 | mel spectrogram | decoded mel → HiFi-GAN → audio |
| **Make-An-Audio 2 Audio VAE** | 2023-05 | 16 kHz | 31.25 Hz | 20 | mel spectrogram | decoded mel → BigVGAN → audio |
| **AudioLDM VAE** | 2023-01 | 16 kHz | 25 Hz | 128 | mel spectrogram | decoded mel → HiFi-GAN → audio |
| **Make-An-Audio VAE** | 2023-01 | 16 kHz | 7.8 Hz | 40 | mel spectrogram | decoded mel → HiFi-GAN → audio |

**Architecture and resources**

| Model | Architecture | Encoder / Decoder | Paper | Code | Weights |
| --- | --- | --- | --- | --- | --- |
| **OmniVAE audio-only** | CNN | DAC-style Conv1D / DAC-style Conv1D | [paper](https://arxiv.org/abs/2607.23855) | [code](https://github.com/OpenMOSS/OmniVAE) | 🟢 [weights](https://huggingface.co/OpenMOSS-Team/OmniVAE) |
| **Qwen-Audio-3 Shared VAE** | CNN | Stable Audio Open-style Conv1D encoder / Conv1D waveform decoder | [paper](https://arxiv.org/abs/2607.27011) | — | ⚪ — |
| **Qwen-Audio-VAE** | CNN + Transformer | DAC-style causal Conv1D + window-Transformer bottleneck / asymmetric causal ConvTranspose1D decoder | [paper](https://arxiv.org/abs/2607.11738) | — | ⚪ — |
| **AudioCALM Audio VAE** | CNN + Transformer | Strided residual Conv1D + self-attention + patch-[CLS] aggregator / residual Conv1D + self-attention + iSTFT head | [paper](https://arxiv.org/abs/2606.23080) | — | ⚪ — |
| **KVAE-Audio** | CNN | 1-D CNN / 1-D CNN | — | [code](https://github.com/kandinskylab/kvae-audio) | 🟢 [weights](https://huggingface.co/kandinskylab/KVAE-Audio) |
| **STAR-VAE** | N/R | N/R | [paper](https://arxiv.org/abs/2606.23064) | — | ⚪ — |
| **UniSonate Mel-VAE** | CNN | Causal ConvNeXt / mirrored ConvNeXt | [paper](https://arxiv.org/abs/2604.22209) | — | ⚪ — |
| **GenAE** | CNN + Transformer | Early-downsampling separable Conv1D + windowed self-attention / ConvTranspose1D + windowed self-attention | [paper](https://arxiv.org/abs/2602.15749) | — | ⚪ — |
| **Ming-omni-tts continuous tokenizer** | Transformer | Qwen2 Transformer encoder / Transformer + iSTFT decoder | — | [code](https://github.com/inclusionAI/Ming-omni-tts) | 🟢 [weights](https://huggingface.co/inclusionAI/Ming-omni-tts-tokenizer-12Hz) |
| **LTX-2 Audio VAE** | CNN | 2-D CNN / 2-D CNN | — | [code](https://github.com/Lightricks/LTX-2) | 🟢 [weights](https://huggingface.co/Lightricks/LTX-2) |
| **Omni2Sound OOB/Wav VAE** | CNN | Stable Audio-style strided Conv1D + Snake / mirrored Conv1D + Snake | [paper](https://arxiv.org/abs/2601.02731) | [code](https://github.com/omni2sound/Omni2Sound) | 🟢 [weights](https://huggingface.co/Dalision/Omni2Sound) |
| **HunyuanVideo-Foley Audio VAE** | CNN | Enhanced DAC Conv1D / enhanced DAC Conv1D | [paper](https://arxiv.org/abs/2508.16930) | [code](https://github.com/Tencent-Hunyuan/HunyuanVideo-Foley) | 🟢 [weights](https://huggingface.co/tencent/HunyuanVideo-Foley) |
| **Kling-Foley Mel-VAE** | CNN | 32-layer Conv1D mel encoder / mirrored ConvTranspose1D mel decoder | [paper](https://arxiv.org/abs/2506.19774) | — | ⚪ — |
| **MMAudio VAE 16 kHz** | CNN | 1-D temporal CNN / 1-D temporal CNN | [paper](https://arxiv.org/abs/2412.15322) | [code](https://github.com/hkchengrex/MMAudio) | 🟢 [weights](https://huggingface.co/hkchengrex/MMAudio) |
| **MMAudio VAE 44.1 kHz** | CNN | 1-D temporal CNN / 1-D temporal CNN | [paper](https://arxiv.org/abs/2412.15322) | [code](https://github.com/hkchengrex/MMAudio) | 🟢 [weights](https://huggingface.co/hkchengrex/MMAudio) |
| **MultiFoley DAC-VAE** | CNN | DAC-style Conv1D / DAC-style Conv1D | [paper](https://arxiv.org/abs/2411.17698) | — | ⚪ — |
| **DACVAE / Movie Gen Audio Autoencoder** | CNN | DAC-style Conv1D / DAC-style Conv1D | [paper](https://arxiv.org/abs/2410.13720) | [code](https://github.com/facebookresearch/dacvae) | 🟢 [weights](https://huggingface.co/facebook/dacvae-watermarked) |
| **EzAudio 1-D VAE** | CNN | Stable Audio-style Oobleck Conv1D encoder / mirrored Oobleck Conv1D decoder | [paper](https://arxiv.org/abs/2409.10819) | [code](https://github.com/haidog-yaqub/EzAudio) | 🟡 [weights](https://github.com/haidog-yaqub/EzAudio) |
| **StableAudio1.0 / Stable Audio Open VAE** | CNN | Oobleck Conv1D / Oobleck Conv1D | [paper](https://arxiv.org/abs/2407.14358) | [code](https://github.com/Stability-AI/stable-audio-tools) | 🟡 [weights](https://huggingface.co/stabilityai/stable-audio-open-1.0) |
| **Wave-VAE (Stability AI)** | N/R | N/R | — | [code](https://github.com/Stability-AI/stable-audio-tools) | ⚪ — |
| **Auffusion VAE** | CNN | 2-D CNN / 2-D CNN | [paper](https://arxiv.org/abs/2401.01044) | [code](https://github.com/happylittlecat2333/Auffusion) | 🟡 [weights](https://huggingface.co/auffusion/auffusion) |
| **AudioLDM 2 VAE** | CNN | 2-D CNN / 2-D CNN | [paper](https://arxiv.org/abs/2308.05734) | [code](https://github.com/haoheliu/AudioLDM2) | 🟢 [weights](https://huggingface.co/cvssp/audioldm2/tree/main/vae) |
| **Make-An-Audio 2 Audio VAE** | CNN + Transformer | Conv1D + temporal Transformer mel encoder / Conv1D + temporal Transformer mel decoder | [paper](https://arxiv.org/abs/2305.18474) | [code](https://github.com/bytedance/Make-An-Audio-2) | 🟡 [weights](https://huggingface.co/ByteDance/Make-An-Audio-2) |
| **AudioLDM VAE** | CNN | 2-D CNN / 2-D CNN | [paper](https://arxiv.org/abs/2301.12503) | [code](https://github.com/haoheliu/AudioLDM) | 🟡 [weights](https://huggingface.co/cvssp/audioldm-s-full-v2) |
| **Make-An-Audio VAE** | CNN | 2-D CNN / 2-D CNN | [paper](https://arxiv.org/abs/2301.12661) | [code](https://github.com/Text-to-Audio/Make-An-Audio) | 🟡 [weights](https://github.com/Text-to-Audio/Make-An-Audio) |

<p align="right"><a href="#top">↑ Back to top</a></p>

<a id="music"></a>
## 🎵 Music

Autoencoders designed for music generation and representation. **13 models · 10 with weights.**

**Specifications**

| Model | Year–Month | Sample rate | Frame rate | Dim | Input | Output |
| --- | ---: | ---: | ---: | ---: | --- | --- |
| **SAME-L** | 2026-05 | 44.1 kHz | 10.77 Hz | 256 | waveform | waveform |
| **SAME-S** | 2026-05 | 44.1 kHz | 10.77 Hz | 256 | waveform | waveform |
| **ACE-Step 1.5 VAE** | 2026-02 | 48 kHz | 25 Hz | 64 | waveform | waveform |
| **DiffRhythm 2 Music VAE** | 2025-10 | 24 kHz | 5 Hz | 64 | waveform | 48 kHz waveform |
| **CoDiCodec continuous branch** | 2025-09 | 44.1 kHz | 10.77 Hz | 64 | complex STFT | complex STFT → waveform |
| **epsilonar-VAE** | 2025-09 | 44.1 kHz | 43 Hz | N/R | stereo waveform | stereo waveform |
| **ACE-Step DCAE** | 2025-06 | 32 kHz | 10.77 Hz | 128 | mel spectrogram | mel/vocoder → waveform |
| **DiffRhythm VAE** | 2025-03 | 44.1 kHz | 21.53 Hz | 64 | waveform | waveform |
| **Music2Latent** | 2024-08 | 44.1 kHz | 10.77 Hz | 64 | complex STFT | complex STFT → waveform |
| **Descript Audio VAE (community)** | 2024-01 | 44.1 kHz | 86.13 Hz | 128 | waveform | waveform |
| **Moûsai Diffusion Autoencoder** | 2023-01 | 48 kHz | N/R | 32 | magnitude spectrogram | diffusion decoder → stereo waveform |
| **Musika autoencoder** | 2022-08 | 22.05 kHz | 11.89 / 23.78 Hz | 32 / 64 | magnitude spectrogram | magnitude/phase STFT → waveform |
| **RAVE v2 (MusicNet)** | 2021-11 | 44.1 kHz | 21.53 Hz | 16 | waveform | waveform |

**Architecture and resources**

| Model | Architecture | Encoder / Decoder | Paper | Code | Weights |
| --- | --- | --- | --- | --- | --- |
| **SAME-L** | Transformer | Waveform patching + sliding-window Transformer resampler / Transformer resampler + inverse patching | [paper](https://arxiv.org/abs/2605.18613) | [code](https://github.com/Stability-AI/stable-audio-3) | 🟢 [weights](https://huggingface.co/stabilityai/SAME-L) |
| **SAME-S** | Transformer | Waveform patching + chunked Transformer resampler / chunked Transformer resampler + inverse patching | [paper](https://arxiv.org/abs/2605.18613) | [code](https://github.com/Stability-AI/stable-audio-3) | 🟢 [weights](https://huggingface.co/stabilityai/SAME-S) |
| **ACE-Step 1.5 VAE** | CNN | Oobleck-style Conv1D / mirrored Conv1D | [paper](https://arxiv.org/abs/2602.00744) | [code](https://github.com/ace-step/ACE-Step-1.5) | 🟡 [weights](https://huggingface.co/ACE-Step/Ace-Step1.5) |
| **DiffRhythm 2 Music VAE** | CNN + Transformer | Stable Audio 2-style Conv1D encoder / Transformer bottleneck + BigVGAN decoder | [paper](https://arxiv.org/abs/2510.22950) | [code](https://github.com/ASLP-lab/DiffRhythm) | ⚪ — |
| **CoDiCodec continuous branch** | CNN + Transformer | Convolutional STFT patchifier + Transformer summary encoder / Transformer-conditioned consistency U-Net decoder | [paper](https://arxiv.org/abs/2509.09836) | [code](https://github.com/SonyCSLParis/codicodec) | 🟢 [weights](https://pypi.org/project/codicodec/) |
| **epsilonar-VAE** | CNN + Transformer | Strided Conv1D + RoPE Transformer bottleneck / ConvTranspose1D + RoPE Transformer | [paper](https://arxiv.org/abs/2509.14912) | [code](https://huggingface.co/earlab/EAR_VAE) | ⚪ — |
| **ACE-Step DCAE** | CNN | 2-D DCAE encoder / 2-D DCAE decoder | [paper](https://arxiv.org/abs/2506.00045) | [code](https://github.com/ace-step/ACE-Step) | 🟡 [weights](https://huggingface.co/ACE-Step/ACE-Step-v1-3.5B) |
| **DiffRhythm VAE** | CNN | Oobleck Conv1D / Oobleck Conv1D | [paper](https://arxiv.org/abs/2503.01183) | [code](https://github.com/ASLP-lab/DiffRhythm) | 🟢 [weights](https://huggingface.co/ASLP-lab/DiffRhythm-vae) |
| **Music2Latent** | CNN + Transformer | Residual Conv2D/Conv1D + frequency self-attention encoder / mirrored upsampler + NCSN++ consistency U-Net | [paper](https://arxiv.org/abs/2408.06500) | [code](https://github.com/SonyCSLParis/music2latent) | 🟢 [weights](https://huggingface.co/SonyCSLParis/music2latent) |
| **Descript Audio VAE (community)** | CNN | DAC-style Conv1D / DAC-style Conv1D | — | [code](https://github.com/innnky/descript-audio-vae) | 🟢 [weights](https://github.com/innnky/descript-audio-vae) |
| **Moûsai Diffusion Autoencoder** | CNN | 1D convolutional magnitude encoder / diffusion 1D U-Net decoder | [paper](https://arxiv.org/abs/2301.11757) | [code](https://github.com/archinetai/audio-diffusion-pytorch) | ⚪ — |
| **Musika autoencoder** | CNN | Two-level Conv1D spectrogram encoder / two-level Conv1D magnitude-phase decoder + iSTFT | [paper](https://arxiv.org/abs/2208.08706) | [code](https://github.com/marcoppasini/musika) | 🟢 [weights](https://huggingface.co/marcop/musika_ae) |
| **RAVE v2 (MusicNet)** | CNN | Multi-band Conv1D encoder / residual upsampling decoder + waveform/loudness/noise synthesis heads | [paper](https://arxiv.org/abs/2111.05011) | [code](https://github.com/acids-ircam/rave) | 🟢 [weights](https://play.forum.ircam.fr/rave-vst-api/get_model/musicnet) |

<p align="right"><a href="#top">↑ Back to top</a></p>

<a id="singing"></a>
## 🎤 Singing

Singing reconstruction, singing voice synthesis, and voice conversion. **6 models · 2 with weights.**

**Specifications**

| Model | Year–Month | Sample rate | Frame rate | Dim | Input | Output |
| --- | ---: | ---: | ---: | ---: | --- | --- |
| **FM-Singer** | 2026-01 | 44.1 kHz | 86.13 Hz | 192 | score/lyrics + waveform | 44.1 kHz audio |
| **CSSinger** | 2024-12 | 44.1 kHz | 86.13 Hz | 192 | score/lyrics + waveform | 44.1 kHz audio |
| **So-VITS-SVC 4.x** | 2023-05 | 44.1 kHz | 86.13 Hz | 192 | content/F0 + waveform | 44.1 kHz audio |
| **UniSyn** | 2022-12 | 24 kHz | 80 Hz | N/R | score/lyrics + waveform | 24 kHz speech or singing |
| **VISinger 2** | 2022-11 | 44.1 kHz | N/R | 192 | score/lyrics + waveform | 44.1 kHz audio |
| **VISinger** | 2021-10 | 24 kHz | N/R | N/R | score/lyrics + waveform | 24 kHz audio |

**Architecture and resources**

| Model | Architecture | Encoder / Decoder | Paper | Code | Weights |
| --- | --- | --- | --- | --- | --- |
| **FM-Singer** | CNN | WaveNet-style posterior/prior encoders + DDSConv flow / DSP-guided GAN waveform generator | [paper](https://arxiv.org/abs/2601.00217) | [code](https://github.com/alsgur9368/FM-Singer) | 🟢 [weights](https://github.com/alsgur9368/FM-Singer) |
| **CSSinger** | CNN | Causal Conv1D posterior encoder + FFT/ChunkStream prior / causal HiFi-GAN generator | [paper](https://arxiv.org/abs/2412.08918) | — | ⚪ — |
| **So-VITS-SVC 4.x** | CNN | VITS posterior encoder / HiFi-GAN generator | — | [code](https://github.com/RVC-Boss/sovits) | 🟢 [weights](https://github.com/RVC-Boss/sovits) |
| **UniSyn** | CNN | Linear-spectrum extractor + WaveNet residual posterior encoder / ConvTranspose1D + MRF wave decoder | [paper](https://arxiv.org/abs/2212.01546) | — | ⚪ — |
| **VISinger 2** | CNN | 8-layer Conv1D posterior encoder / harmonic-noise DSP synthesizer-conditioned HiFi-GAN | [paper](https://arxiv.org/abs/2211.02903) | — | ⚪ — |
| **VISinger** | CNN | Linear-spectrum extractor + WaveNet residual encoder / HiFi-GAN generator | [paper](https://arxiv.org/abs/2110.08813) | — | ⚪ — |

<p align="right"><a href="#top">↑ Back to top</a></p>

<a id="speech"></a>
## 🗣️ Speech

Speech reconstruction and conditional text-to-speech VAEs. **12 models · 10 with weights.**

**Specifications**

| Model | Year–Month | Sample rate | Frame rate | Dim | Input | Output |
| --- | ---: | ---: | ---: | ---: | --- | --- |
| **dots.tts AudioVAE** | 2026-06 | 48 kHz | 25 Hz | 128 | waveform | waveform |
| **VoxCPM2 AudioVAE** | 2026-06 | 16 kHz | 25 Hz | 64 | waveform | 48 kHz waveform |
| **HoliTok** | 2026-05 | 48 kHz | 25 Hz | 128 | waveform | waveform |
| **LongCat Wav-VAE** | 2026-03 | 24 kHz | 11.72 Hz | 64 | waveform | waveform |
| **MingTok-Audio** | 2025-11 | 16 kHz | 50 Hz | 64 | waveform | complex STFT → waveform |
| **SALAD-VAE** | 2025-10 | N/R | 7.8 Hz | 64 / 128 | complex STFT | complex STFT → waveform |
| **Semantic-VAE** | 2025-09 | 16 kHz | 40 Hz | 64 | condition + waveform | waveform |
| **Semantic-VAE-600k** | 2025-09 | 16 kHz | 40 Hz | 64 | condition + waveform | waveform |
| **Semantic-VAE-A16** | 2025-09 | 16 kHz | 40 Hz | 16 | condition + waveform | waveform |
| **Semantic-VAE-A64** | 2025-09 | 16 kHz | 40 Hz | 64 | condition + waveform | waveform |
| **VoxCPM AudioVAE** | 2025-09 | 16 kHz | 25 Hz | 64 | waveform | waveform |
| **VibeVoice Acoustic Tokenizer** | 2025-08 | 24 kHz | 7.5 Hz | 64 | waveform | waveform |

**Architecture and resources**

| Model | Architecture | Encoder / Decoder | Paper | Code | Weights |
| --- | --- | --- | --- | --- | --- |
| **dots.tts AudioVAE** | CNN | Strided causal residual Conv1D posterior encoder / causal BigVGAN-v2 decoder | [paper](https://arxiv.org/abs/2606.07080) | [code](https://github.com/studio-dots-ai/dots.tts) | 🟡 [weights](https://huggingface.co/rednote-hilab/dots.tts-base) |
| **VoxCPM2 AudioVAE** | CNN | Strided causal DAC-style Conv1D encoder / deeper sample-rate-conditioned causal Conv1D decoder | [paper](https://arxiv.org/abs/2606.06928) | [code](https://github.com/OpenBMB/VoxCPM) | 🟡 [weights](https://huggingface.co/openbmb/VoxCPM2) |
| **HoliTok** | CNN | Strided causal residual Conv1D + LSTM bottleneck + normalizing flow / mirrored BigVGAN AMPBlock decoder | [paper](https://arxiv.org/abs/2605.29948) | [code](https://github.com/bovod-sjtu/HoliTok) | 🟡 [weights](https://github.com/bovod-sjtu/HoliTok) |
| **LongCat Wav-VAE** | CNN | Oobleck dilated residual Conv1D + space-to-channel shortcuts / mirrored ConvTranspose1D + channel-to-space shortcuts | [paper](https://arxiv.org/abs/2603.29339) | [code](https://github.com/meituan-longcat/LongCat-AudioDiT) | 🟡 [weights](https://huggingface.co/meituan-longcat/LongCat-AudioDiT-3.5B) |
| **MingTok-Audio** | Transformer | Waveform framing + causal Transformer encoder / causal Transformer + Vocos-style complex-STFT iSTFT head | [paper](https://arxiv.org/abs/2511.05516) | [code](https://github.com/inclusionAI/Ming-UniAudio) | 🟢 [weights](https://huggingface.co/inclusionAI/MingTok-Audio) |
| **SALAD-VAE** | CNN | Centered dilated inverted-bottleneck Conv2D encoder / causal mirrored Conv2D decoder | [paper](https://arxiv.org/abs/2510.07592) | — | ⚪ — |
| **Semantic-VAE** | CNN | DAC-style Conv1D / BigVGAN decoder | [paper](https://arxiv.org/abs/2509.22167) | [code](https://github.com/ZhikangNiu/Semantic-VAE) | 🟢 [weights](https://huggingface.co/zkniu/Semantic-VAE) |
| **Semantic-VAE-600k** | CNN | DAC-style Conv1D / BigVGAN decoder | [paper](https://arxiv.org/abs/2509.22167) | [code](https://github.com/ZhikangNiu/Semantic-VAE) | ⚪ — |
| **Semantic-VAE-A16** | CNN | DAC-style Conv1D / BigVGAN decoder | [paper](https://arxiv.org/abs/2509.22167) | [code](https://github.com/ZhikangNiu/Semantic-VAE) | 🟢 [weights](https://huggingface.co/zkniu/Semantic-VAE/tree/main/acoustic_vae_dim16) |
| **Semantic-VAE-A64** | CNN | DAC-style Conv1D / BigVGAN decoder | [paper](https://arxiv.org/abs/2509.22167) | [code](https://github.com/ZhikangNiu/Semantic-VAE) | 🟢 [weights](https://huggingface.co/zkniu/Semantic-VAE/tree/main/acoustic_vae_dim64) |
| **VoxCPM AudioVAE** | CNN | Causal Conv1D / causal ConvTranspose1D | [paper](https://arxiv.org/abs/2509.24650) | [code](https://github.com/OpenBMB/VoxCPM) | 🟢 [weights](https://huggingface.co/openbmb/VoxCPM-0.5B/blob/main/audiovae.pth) |
| **VibeVoice Acoustic Tokenizer** | CNN | 7-stage depthwise causal Conv1D hierarchy / mirror-symmetric causal Conv1D decoder | [paper](https://arxiv.org/abs/2508.19205) | [code](https://github.com/microsoft/VibeVoice) | 🟢 [weights](https://huggingface.co/microsoft/VibeVoice-AcousticTokenizer) |

<p align="right"><a href="#top">↑ Back to top</a></p>
