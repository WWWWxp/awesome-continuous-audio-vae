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

- **Frame rate**: latent time steps produced per second of input audio.
- **Dim**: final latent width at each time step; 2-D mel latents are flattened across channel and frequency.
- **Weights**: 🟢 standalone component · 🟡 bundled in a larger checkpoint · ⚪ unavailable.
- **N/R**: not reported in the linked paper, code, or checkpoint configuration.

<a id="audio"></a>
## 🔊 Audio / Sound

General audio, environmental sound, Foley, and multi-domain reconstruction. **25 models · 16 with weights.**

| Model | Type | Year | Frame rate | Dim | Encoder / Decoder Architecture | I/O | Paper | Code | Weights |
| --- | --- | ---: | ---: | ---: | --- | --- | --- | --- | --- |
| **AudioCALM Audio VAE** | `VAE` | 2026 | `N/R` | `N/R` | N/R | waveform → latent → waveform | [paper](https://arxiv.org/abs/2606.23080) | — | ⚪ — |
| **GenAE** | `AE` | 2026 | `N/R` | `N/R` | N/R | SR N/R waveform → latent → waveform | [paper](https://arxiv.org/abs/2602.15749) | — | ⚪ — |
| **KVAE-Audio** | `VAE` | 2026 | `50 Hz` | `64` | 1-D CNN / 1-D CNN | 48 kHz waveform → latent → waveform | — | [code](https://github.com/kandinskylab/kvae-audio) | 🟢 [weights](https://huggingface.co/kandinskylab/KVAE-Audio) |
| **LTX-2 Audio VAE** | `KL-VAE` | 2026 | `25 Hz` | `128` | 2-D CNN / 2-D CNN | 16 kHz stereo mel → latent → decoded mel → stereo vocoder → 24 kHz stereo waveform | — | [code](https://github.com/Lightricks/LTX-2) | 🟢 [weights](https://huggingface.co/Lightricks/LTX-2) |
| **Ming-omni-tts continuous tokenizer** | `VAE` | 2026 | `12.5 Hz` | `64` | Qwen2 Transformer encoder / Transformer + iSTFT decoder | 44.1 kHz waveform → latent → waveform | — | [code](https://github.com/inclusionAI/Ming-omni-tts) | 🟢 [weights](https://huggingface.co/inclusionAI/Ming-omni-tts-tokenizer-12Hz) |
| **Omni2Sound OOB/Wav VAE** | `VAE` | 2026 | `25 Hz` | `64` | 1-D CNN / 1-D CNN | 16 kHz waveform → latent → waveform | [paper](https://arxiv.org/abs/2601.02731) | [code](https://github.com/omni2sound/Omni2Sound) | 🟢 [weights](https://huggingface.co/Dalision/Omni2Sound) |
| **OmniVAE audio-only** | `VAE` | 2026 | `50 Hz` | `128` | DAC-style Conv1D / DAC-style Conv1D | 48 kHz waveform → latent → waveform | [paper](https://arxiv.org/abs/2607.23855) | [code](https://github.com/OpenMOSS/OmniVAE) | 🟢 [weights](https://huggingface.co/OpenMOSS-Team/OmniVAE) |
| **Qwen-Audio-3 Shared VAE** | `VAE` | 2026 | `N/R` | `N/R` | N/R | 48 kHz stereo waveform → latent → stereo waveform | [paper](https://arxiv.org/abs/2607.27011) | — | ⚪ — |
| **Qwen-Audio-VAE** | `VAE-GAN` | 2026 | `12.5 Hz` | `128` | Conv1D / Conv1D | 24 kHz waveform → latent → waveform | [paper](https://arxiv.org/abs/2607.11738) | — | ⚪ — |
| **STAR-VAE** | `VAE` | 2026 | `N/R` | `N/R` | N/R | SR N/R waveform → latent → waveform | [paper](https://star-vae.github.io/) | — | ⚪ — |
| **UniSonate Mel-VAE** | `VAE` | 2026 | `43 Hz` | `40` | Causal ConvNeXt / mirrored ConvNeXt | 44.1 kHz audio/mel → latent → decoded mel → vocoder → audio | [paper](https://arxiv.org/abs/2604.22209) | — | ⚪ — |
| **HunyuanVideo-Foley Audio VAE** | `VAE-GAN` | 2025 | `50 Hz` | `128` | Enhanced DAC Conv1D / enhanced DAC Conv1D | 48 kHz waveform → latent → waveform | [paper](https://arxiv.org/abs/2508.16930) | [code](https://github.com/Tencent-Hunyuan/HunyuanVideo-Foley) | 🟢 [weights](https://huggingface.co/tencent/HunyuanVideo-Foley) |
| **Kling-Foley Mel-VAE** | `VAE-GAN` | 2025 | `43 Hz` | `40` | 2-D CNN / 2-D CNN | 44.1 kHz audio/mel → latent → decoded mel → vocoder → audio | [paper](https://arxiv.org/abs/2506.19774) | — | ⚪ — |
| **MultiFoley DAC-VAE** | `VAE-GAN` | 2025 | `40 Hz` | `64` | DAC-style Conv1D / DAC-style Conv1D | 48 kHz waveform → latent → waveform | [paper](https://arxiv.org/abs/2411.17698) | — | ⚪ — |
| **Auffusion VAE** | `VAE` | 2024 | `12.5 Hz` | `128` | 2-D CNN / 2-D CNN | 16 kHz audio/mel → latent → decoded mel → HiFi-GAN → audio | [paper](https://arxiv.org/abs/2401.01044) | [code](https://github.com/happylittlecat2333/Auffusion) | 🟡 [weights](https://huggingface.co/auffusion/auffusion) |
| **DACVAE / Movie Gen Audio Autoencoder** | `VAE-GAN` | 2024 | `25 Hz` | `128` | DAC-style Conv1D / DAC-style Conv1D | 48 kHz waveform → latent → waveform | [paper](https://arxiv.org/abs/2410.13720) | [code](https://github.com/facebookresearch/dacvae) | 🟢 [weights](https://huggingface.co/facebook/dacvae-watermarked) |
| **EzAudio 1-D VAE** | `VAE` | 2024 | `50 Hz` | `128` | 1-D CNN / 1-D CNN | 24 kHz waveform → latent → waveform | [paper](https://arxiv.org/abs/2409.10819) | [code](https://github.com/haidog-yaqub/EzAudio) | 🟡 [weights](https://github.com/haidog-yaqub/EzAudio) |
| **MMAudio VAE 16 kHz** | `VAE` | 2024 | `31.25 Hz` | `20` | 1-D temporal CNN / 1-D temporal CNN | 16 kHz audio/mel → latent → decoded mel → BigVGAN → audio | [paper](https://arxiv.org/abs/2412.15322) | [code](https://github.com/hkchengrex/MMAudio) | 🟢 [weights](https://huggingface.co/hkchengrex/MMAudio) |
| **MMAudio VAE 44.1 kHz** | `VAE` | 2024 | `43.07 Hz` | `40` | 1-D temporal CNN / 1-D temporal CNN | 44.1 kHz audio/mel → latent → decoded mel → BigVGAN → audio | [paper](https://arxiv.org/abs/2412.15322) | [code](https://github.com/hkchengrex/MMAudio) | 🟢 [weights](https://huggingface.co/hkchengrex/MMAudio) |
| **StableAudio1.0 / Stable Audio Open VAE** | `VAE` | 2024 | `21 Hz` | `64` | Oobleck Conv1D / Oobleck Conv1D | 44.1 kHz waveform → latent → waveform | [paper](https://arxiv.org/abs/2407.14358) | [code](https://github.com/Stability-AI/stable-audio-tools) | 🟡 [weights](https://huggingface.co/stabilityai/stable-audio-open-1.0) |
| **Wave-VAE (Stability AI)** | `VAE` | 2024 | `21 Hz` | `64` | N/R | 44.1 kHz waveform → latent → waveform | — | [code](https://github.com/Stability-AI/stable-audio-tools) | ⚪ — |
| **AudioLDM 2 VAE** | `KL-VAE` | 2023 | `25 Hz` | `128` | 2-D CNN / 2-D CNN | 16 kHz audio/mel → latent → decoded mel → HiFi-GAN → audio | [paper](https://arxiv.org/abs/2308.05734) | [code](https://github.com/haoheliu/AudioLDM2) | 🟢 [weights](https://huggingface.co/cvssp/audioldm2/tree/main/vae) |
| **AudioLDM VAE** | `KL-VAE` | 2023 | `25 Hz` | `128` | 2-D CNN / 2-D CNN | 16 kHz audio/mel → latent → decoded mel → HiFi-GAN → audio | [paper](https://arxiv.org/abs/2301.12503) | [code](https://github.com/haoheliu/AudioLDM) | 🟡 [weights](https://huggingface.co/cvssp/audioldm-s-full-v2) |
| **Make-An-Audio 2 Audio VAE** | `VAE` | 2023 | `31.25 Hz` | `20` | 1-D CNN + temporal Transformer / 1-D CNN | 16 kHz audio/mel → latent → decoded mel → BigVGAN → audio | [paper](https://arxiv.org/abs/2305.18474) | [code](https://github.com/bytedance/Make-An-Audio-2) | 🟡 [weights](https://huggingface.co/ByteDance/Make-An-Audio-2) |
| **Make-An-Audio VAE** | `VAE` | 2023 | `7.8 Hz` | `40` | 2-D CNN / 2-D CNN | 16 kHz audio/mel → latent → decoded mel → BigVGAN → audio | [paper](https://arxiv.org/abs/2301.12661) | [code](https://github.com/Text-to-Audio/Make-An-Audio) | 🟡 [weights](https://github.com/Text-to-Audio/Make-An-Audio) |

<p align="right"><a href="#top">↑ Back to top</a></p>

<a id="music"></a>
## 🎵 Music

Autoencoders designed for music generation and representation. **13 models · 10 with weights.**

| Model | Type | Year | Frame rate | Dim | Encoder / Decoder Architecture | I/O | Paper | Code | Weights |
| --- | --- | ---: | ---: | ---: | --- | --- | --- | --- | --- |
| **ACE-Step 1.5 VAE** | `VAE/AE` | 2026 | `25 Hz` | `64` | Oobleck-style Conv1D / mirrored Conv1D | 48 kHz waveform → latent → waveform | [paper](https://arxiv.org/abs/2602.00744) | [code](https://github.com/ace-step/ACE-Step-1.5) | 🟡 [weights](https://huggingface.co/ACE-Step/Ace-Step1.5) |
| **SAME-L** | `AE` | 2026 | `10.77 Hz` | `256` | Oobleck Conv1D / Oobleck Conv1D | 44.1 kHz waveform → latent → waveform | [paper](https://arxiv.org/abs/2605.18613) | [code](https://github.com/Stability-AI/stable-audio-3) | 🟢 [weights](https://huggingface.co/stabilityai/SAME-L) |
| **SAME-S** | `AE` | 2026 | `10.77 Hz` | `256` | Transformer / Conv1D | 44.1 kHz waveform → latent → waveform | [paper](https://arxiv.org/abs/2605.18613) | [code](https://github.com/Stability-AI/stable-audio-3) | 🟢 [weights](https://huggingface.co/stabilityai/SAME-S) |
| **ACE-Step DCAE** | `AE` | 2025 | `10.77 Hz` | `128` | 2-D DCAE encoder / 2-D DCAE decoder | 48 kHz waveform → 44.1 kHz mel → latent → mel/vocoder → waveform | [paper](https://arxiv.org/abs/2506.00045) | [code](https://github.com/ace-step/ACE-Step) | 🟡 [weights](https://huggingface.co/ACE-Step/ACE-Step-v1-3.5B) |
| **CoDiCodec continuous branch** | `Hybrid AE` | 2025 | `10.77 Hz` | `64` | Conv1D / Conv1D | 44.1 kHz waveform → latent → waveform | [paper](https://arxiv.org/abs/2509.09836) | [code](https://github.com/SonyCSLParis/codicodec) | 🟢 [weights](https://pypi.org/project/codicodec/) |
| **DiffRhythm 2 Music VAE** | `VAE` | 2025 | `5 Hz` | `N/R` | DAC-style Conv1D / BigVGAN decoder | 16 kHz waveform → latent → waveform | [paper](https://arxiv.org/abs/2510.22950) | [code](https://github.com/ASLP-lab/DiffRhythm) | ⚪ — |
| **DiffRhythm VAE** | `VAE` | 2025 | `21.53 Hz` | `128` | Oobleck Conv1D / Oobleck Conv1D | 44.1 kHz waveform → latent → waveform | [paper](https://arxiv.org/abs/2503.01183) | [code](https://github.com/ASLP-lab/DiffRhythm) | 🟢 [weights](https://huggingface.co/ASLP-lab/DiffRhythm-vae) |
| **epsilonar-VAE** | `VAE-GAN` | 2025 | `N/R` | `N/R` | N/R | 44.1 kHz waveform → latent → waveform | [paper](https://arxiv.org/abs/2509.14912) | [code](https://huggingface.co/earlab/EAR_VAE) | ⚪ — |
| **Music2Latent** | `Consistency AE` | 2024 | `10.77 Hz` | `64` | Multi-scale CNN / multi-scale CNN | 44.1 kHz waveform → latent → waveform | [paper](https://arxiv.org/abs/2408.06500) | [code](https://github.com/SonyCSLParis/music2latent) | 🟢 [weights](https://huggingface.co/SonyCSLParis/music2latent) |
| **Descript Audio VAE (community)** | `VAE-GAN` | 2023 | `86.13 Hz` | `128` | DAC-style Conv1D / DAC-style Conv1D | 44.1 kHz waveform → latent → waveform | — | [code](https://github.com/innnky/descript-audio-vae) | 🟢 [weights](https://github.com/innnky/descript-audio-vae) |
| **Moûsai Diffusion Autoencoder** | `AE` | 2023 | `N/R` | `N/R` | N/R | 48 kHz waveform → latent → waveform | [paper](https://arxiv.org/abs/2301.11757) | [code](https://github.com/archinetai/audio-diffusion-pytorch) | ⚪ — |
| **RAVE v2 (MusicNet)** | `VAE/WAE` | 2023 | `21.53 Hz` | `16` | Residual Conv1D / residual ConvTranspose1D | 44.1 kHz waveform → latent → waveform | [paper](https://arxiv.org/abs/2111.05011) | [code](https://github.com/acids-ircam/rave) | 🟢 [weights](https://play.forum.ircam.fr/rave-vst-api/get_model/musicnet) |
| **Musika autoencoder** | `Hierarchical AE` | 2022 | `10.77 Hz` | `64` | Hierarchical CNN / hierarchical CNN | 44.1 kHz audio/mel → latent → audio | [paper](https://arxiv.org/abs/2208.08706) | [code](https://github.com/marcoppasini/musika) | 🟢 [weights](https://huggingface.co/marcop/musika_ae) |

<p align="right"><a href="#top">↑ Back to top</a></p>

<a id="singing"></a>
## 🎤 Singing

Singing reconstruction, singing voice synthesis, and voice conversion. **6 models · 2 with weights.**

| Model | Type | Year | Frame rate | Dim | Encoder / Decoder Architecture | I/O | Paper | Code | Weights |
| --- | --- | ---: | ---: | ---: | --- | --- | --- | --- | --- |
| **FM-Singer** | `cVAE + Flow` | 2026 | `86.13 Hz` | `384` | VITS posterior encoder / HiFi-GAN generator | score/lyrics + 44.1 kHz audio → latent → 44.1 kHz audio | [paper](https://arxiv.org/abs/2601.00217) | [code](https://github.com/alsgur9368/FM-Singer) | 🟢 [weights](https://github.com/alsgur9368/FM-Singer) |
| **CSSinger** | `cVAE` | 2024 | `N/R` | `N/R` | N/R | score/lyrics + audio → SR N/R audio | [paper](https://arxiv.org/abs/2412.08918) | — | ⚪ — |
| **So-VITS-SVC 4.x** | `cVAE` | 2023 | `86.13 Hz` | `192` | VITS posterior encoder / HiFi-GAN generator | content/F0 + 44.1 kHz audio → latent → 44.1 kHz audio | — | [code](https://github.com/RVC-Boss/sovits) | 🟢 [weights](https://github.com/RVC-Boss/sovits) |
| **UniSyn** | `cVAE` | 2022 | `N/R` | `N/R` | VITS posterior encoder / HiFi-GAN generator | text/score + audio → latent → speech or singing | [paper](https://arxiv.org/abs/2212.01546) | — | ⚪ — |
| **VISinger 2** | `cVAE` | 2022 | `N/R` | `N/R` | VITS posterior encoder / HiFi-GAN generator | score/lyrics + audio → SR N/R audio | [paper](https://arxiv.org/abs/2211.02903) | — | ⚪ — |
| **VISinger** | `cVAE` | 2021 | `N/R` | `N/R` | VITS posterior encoder / HiFi-GAN generator | score/lyrics + audio → SR N/R audio | [paper](https://arxiv.org/abs/2110.08813) | — | ⚪ — |

<p align="right"><a href="#top">↑ Back to top</a></p>

<a id="speech"></a>
## 🗣️ Speech

Speech reconstruction and conditional text-to-speech VAEs. **12 models · 10 with weights.**

| Model | Type | Year | Frame rate | Dim | Encoder / Decoder Architecture | I/O | Paper | Code | Weights |
| --- | --- | ---: | ---: | ---: | --- | --- | --- | --- | --- |
| **dots.tts AudioVAE** | `VAE` | 2026 | `25 Hz` | `128` | Causal Conv1D / causal BigVGAN generator | 48 kHz waveform → latent → waveform | [paper](https://arxiv.org/abs/2606.07080) | [code](https://github.com/studio-dots-ai/dots.tts) | 🟡 [weights](https://huggingface.co/rednote-hilab/dots.tts-base) |
| **HoliTok** | `VAE` | 2026 | `25 Hz` | `128` | Conv1D / BigVGAN-style generator | 48 kHz waveform → latent → waveform | [paper](https://arxiv.org/abs/2605.29948) | [code](https://github.com/bovod-sjtu/HoliTok) | 🟡 [weights](https://github.com/bovod-sjtu/HoliTok) |
| **LongCat Wav-VAE** | `VAE` | 2026 | `12 Hz` | `64` | Residual Conv1D / residual ConvTranspose1D | 24 kHz waveform → latent → waveform | [paper](https://arxiv.org/abs/2603.29339) | [code](https://github.com/meituan-longcat/LongCat-AudioDiT) | 🟡 [weights](https://huggingface.co/meituan-longcat/LongCat-AudioDiT-3.5B) |
| **SALAD-VAE** | `VAE` | 2026 | `N/R` | `N/R` | N/R | waveform → latent → waveform | [paper](https://arxiv.org/abs/2510.07592) | — | ⚪ — |
| **VoxCPM2 AudioVAE** | `VAE` | 2026 | `25 Hz` | `64` | DAC-style Conv1D encoder / sample-rate-conditioned Conv1D decoder | 16 kHz waveform → latent → 48 kHz waveform | [paper](https://openreview.net/forum?id=h5KLpGoqzC) | [code](https://github.com/OpenBMB/VoxCPM) | 🟡 [weights](https://huggingface.co/openbmb/VoxCPM2) |
| **MingTok-Audio** | `VAE` | 2025 | `50 Hz` | `64` | Causal Transformer / Transformer | 16 kHz waveform → latent → waveform | [paper](https://arxiv.org/abs/2511.05516) | [code](https://github.com/inclusionAI/Ming-UniAudio) | 🟢 [weights](https://huggingface.co/inclusionAI/MingTok-Audio) |
| **Semantic-VAE** | `Semantic cVAE` | 2025 | `40 Hz` | `64` | DAC-style Conv1D / BigVGAN decoder | 16 kHz waveform → latent → waveform | [paper](https://arxiv.org/abs/2509.22167) | [code](https://github.com/ZhikangNiu/Semantic-VAE) | 🟢 [weights](https://huggingface.co/zkniu/Semantic-VAE) |
| **Semantic-VAE-600k** | `Semantic cVAE` | 2025 | `40 Hz` | `64` | DAC-style Conv1D / BigVGAN decoder | 16 kHz waveform → latent → waveform | [paper](https://arxiv.org/abs/2509.22167) | [code](https://github.com/ZhikangNiu/Semantic-VAE) | ⚪ — |
| **Semantic-VAE-A16** | `Semantic cVAE` | 2025 | `40 Hz` | `16` | DAC-style Conv1D / BigVGAN decoder | 16 kHz waveform → latent → waveform | [paper](https://arxiv.org/abs/2509.22167) | [code](https://github.com/ZhikangNiu/Semantic-VAE) | 🟢 [weights](https://huggingface.co/zkniu/Semantic-VAE/tree/main/acoustic_vae_dim16) |
| **Semantic-VAE-A64** | `Semantic cVAE` | 2025 | `40 Hz` | `64` | DAC-style Conv1D / BigVGAN decoder | 16 kHz waveform → latent → waveform | [paper](https://arxiv.org/abs/2509.22167) | [code](https://github.com/ZhikangNiu/Semantic-VAE) | 🟢 [weights](https://huggingface.co/zkniu/Semantic-VAE/tree/main/acoustic_vae_dim64) |
| **VibeVoice Acoustic Tokenizer** | `σ-VAE` | 2025 | `7.5 Hz` | `64` | 7-stage causal ConvNeXt / mirrored ConvNeXt | 24 kHz waveform → latent → waveform | [paper](https://openreview.net/forum?id=d714a618b7e734ac60c3c083956a2017ed47e54c) | [code](https://github.com/microsoft/VibeVoice) | 🟢 [weights](https://huggingface.co/microsoft/VibeVoice-AcousticTokenizer) |
| **VoxCPM AudioVAE** | `VAE` | 2025 | `25 Hz` | `64` | Causal Conv1D / causal ConvTranspose1D | 16 kHz waveform → latent → waveform | [paper](https://arxiv.org/abs/2509.24650) | [code](https://github.com/OpenBMB/VoxCPM) | 🟢 [weights](https://huggingface.co/openbmb/VoxCPM-0.5B/blob/main/audiovae.pth) |

<p align="right"><a href="#top">↑ Back to top</a></p>
