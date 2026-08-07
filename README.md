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
- **Architecture**: coarse encoder/decoder backbone family.
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

| Model and resources | Architecture |
| --- | --- |
| **OmniVAE audio-only** · [Paper](https://arxiv.org/abs/2607.23855) · [Code](https://github.com/OpenMOSS/OmniVAE) · 🟢 [Weights](https://huggingface.co/OpenMOSS-Team/OmniVAE) | CNN |
| **Qwen-Audio-3 Shared VAE** · [Paper](https://arxiv.org/abs/2607.27011) · Code — · ⚪ Weights — | CNN |
| **Qwen-Audio-VAE** · [Paper](https://arxiv.org/abs/2607.11738) · Code — · ⚪ Weights — | CNN + Transformer |
| **AudioCALM Audio VAE** · [Paper](https://arxiv.org/abs/2606.23080) · Code — · ⚪ Weights — | CNN + Transformer |
| **KVAE-Audio** · Paper — · [Code](https://github.com/kandinskylab/kvae-audio) · 🟢 [Weights](https://huggingface.co/kandinskylab/KVAE-Audio) | CNN |
| **STAR-VAE** · [Paper](https://arxiv.org/abs/2606.23064) · Code — · ⚪ Weights — | N/R |
| **UniSonate Mel-VAE** · [Paper](https://arxiv.org/abs/2604.22209) · Code — · ⚪ Weights — | CNN |
| **GenAE** · [Paper](https://arxiv.org/abs/2602.15749) · Code — · ⚪ Weights — | CNN + Transformer |
| **Ming-omni-tts continuous tokenizer** · Paper — · [Code](https://github.com/inclusionAI/Ming-omni-tts) · 🟢 [Weights](https://huggingface.co/inclusionAI/Ming-omni-tts-tokenizer-12Hz) | Transformer |
| **LTX-2 Audio VAE** · Paper — · [Code](https://github.com/Lightricks/LTX-2) · 🟢 [Weights](https://huggingface.co/Lightricks/LTX-2) | CNN |
| **Omni2Sound OOB/Wav VAE** · [Paper](https://arxiv.org/abs/2601.02731) · [Code](https://github.com/omni2sound/Omni2Sound) · 🟢 [Weights](https://huggingface.co/Dalision/Omni2Sound) | CNN |
| **HunyuanVideo-Foley Audio VAE** · [Paper](https://arxiv.org/abs/2508.16930) · [Code](https://github.com/Tencent-Hunyuan/HunyuanVideo-Foley) · 🟢 [Weights](https://huggingface.co/tencent/HunyuanVideo-Foley) | CNN |
| **Kling-Foley Mel-VAE** · [Paper](https://arxiv.org/abs/2506.19774) · Code — · ⚪ Weights — | CNN |
| **MMAudio VAE 16 kHz** · [Paper](https://arxiv.org/abs/2412.15322) · [Code](https://github.com/hkchengrex/MMAudio) · 🟢 [Weights](https://huggingface.co/hkchengrex/MMAudio) | CNN |
| **MMAudio VAE 44.1 kHz** · [Paper](https://arxiv.org/abs/2412.15322) · [Code](https://github.com/hkchengrex/MMAudio) · 🟢 [Weights](https://huggingface.co/hkchengrex/MMAudio) | CNN |
| **MultiFoley DAC-VAE** · [Paper](https://arxiv.org/abs/2411.17698) · Code — · ⚪ Weights — | CNN |
| **DACVAE / Movie Gen Audio Autoencoder** · [Paper](https://arxiv.org/abs/2410.13720) · [Code](https://github.com/facebookresearch/dacvae) · 🟢 [Weights](https://huggingface.co/facebook/dacvae-watermarked) | CNN |
| **EzAudio 1-D VAE** · [Paper](https://arxiv.org/abs/2409.10819) · [Code](https://github.com/haidog-yaqub/EzAudio) · 🟡 [Weights](https://github.com/haidog-yaqub/EzAudio) | CNN |
| **StableAudio1.0 / Stable Audio Open VAE** · [Paper](https://arxiv.org/abs/2407.14358) · [Code](https://github.com/Stability-AI/stable-audio-tools) · 🟡 [Weights](https://huggingface.co/stabilityai/stable-audio-open-1.0) | CNN |
| **Wave-VAE (Stability AI)** · Paper — · [Code](https://github.com/Stability-AI/stable-audio-tools) · ⚪ Weights — | N/R |
| **Auffusion VAE** · [Paper](https://arxiv.org/abs/2401.01044) · [Code](https://github.com/happylittlecat2333/Auffusion) · 🟡 [Weights](https://huggingface.co/auffusion/auffusion) | CNN |
| **AudioLDM 2 VAE** · [Paper](https://arxiv.org/abs/2308.05734) · [Code](https://github.com/haoheliu/AudioLDM2) · 🟢 [Weights](https://huggingface.co/cvssp/audioldm2/tree/main/vae) | CNN |
| **Make-An-Audio 2 Audio VAE** · [Paper](https://arxiv.org/abs/2305.18474) · [Code](https://github.com/bytedance/Make-An-Audio-2) · 🟡 [Weights](https://huggingface.co/ByteDance/Make-An-Audio-2) | CNN + Transformer |
| **AudioLDM VAE** · [Paper](https://arxiv.org/abs/2301.12503) · [Code](https://github.com/haoheliu/AudioLDM) · 🟡 [Weights](https://huggingface.co/cvssp/audioldm-s-full-v2) | CNN |
| **Make-An-Audio VAE** · [Paper](https://arxiv.org/abs/2301.12661) · [Code](https://github.com/Text-to-Audio/Make-An-Audio) · 🟡 [Weights](https://github.com/Text-to-Audio/Make-An-Audio) | CNN |

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

| Model and resources | Architecture |
| --- | --- |
| **SAME-L** · [Paper](https://arxiv.org/abs/2605.18613) · [Code](https://github.com/Stability-AI/stable-audio-3) · 🟢 [Weights](https://huggingface.co/stabilityai/SAME-L) | Transformer |
| **SAME-S** · [Paper](https://arxiv.org/abs/2605.18613) · [Code](https://github.com/Stability-AI/stable-audio-3) · 🟢 [Weights](https://huggingface.co/stabilityai/SAME-S) | Transformer |
| **ACE-Step 1.5 VAE** · [Paper](https://arxiv.org/abs/2602.00744) · [Code](https://github.com/ace-step/ACE-Step-1.5) · 🟡 [Weights](https://huggingface.co/ACE-Step/Ace-Step1.5) | CNN |
| **DiffRhythm 2 Music VAE** · [Paper](https://arxiv.org/abs/2510.22950) · [Code](https://github.com/ASLP-lab/DiffRhythm) · ⚪ Weights — | CNN + Transformer |
| **CoDiCodec continuous branch** · [Paper](https://arxiv.org/abs/2509.09836) · [Code](https://github.com/SonyCSLParis/codicodec) · 🟢 [Weights](https://pypi.org/project/codicodec/) | CNN + Transformer |
| **epsilonar-VAE** · [Paper](https://arxiv.org/abs/2509.14912) · [Code](https://huggingface.co/earlab/EAR_VAE) · ⚪ Weights — | CNN + Transformer |
| **ACE-Step DCAE** · [Paper](https://arxiv.org/abs/2506.00045) · [Code](https://github.com/ace-step/ACE-Step) · 🟡 [Weights](https://huggingface.co/ACE-Step/ACE-Step-v1-3.5B) | CNN |
| **DiffRhythm VAE** · [Paper](https://arxiv.org/abs/2503.01183) · [Code](https://github.com/ASLP-lab/DiffRhythm) · 🟢 [Weights](https://huggingface.co/ASLP-lab/DiffRhythm-vae) | CNN |
| **Music2Latent** · [Paper](https://arxiv.org/abs/2408.06500) · [Code](https://github.com/SonyCSLParis/music2latent) · 🟢 [Weights](https://huggingface.co/SonyCSLParis/music2latent) | CNN + Transformer |
| **Descript Audio VAE (community)** · Paper — · [Code](https://github.com/innnky/descript-audio-vae) · 🟢 [Weights](https://github.com/innnky/descript-audio-vae) | CNN |
| **Moûsai Diffusion Autoencoder** · [Paper](https://arxiv.org/abs/2301.11757) · [Code](https://github.com/archinetai/audio-diffusion-pytorch) · ⚪ Weights — | CNN |
| **Musika autoencoder** · [Paper](https://arxiv.org/abs/2208.08706) · [Code](https://github.com/marcoppasini/musika) · 🟢 [Weights](https://huggingface.co/marcop/musika_ae) | CNN |
| **RAVE v2 (MusicNet)** · [Paper](https://arxiv.org/abs/2111.05011) · [Code](https://github.com/acids-ircam/rave) · 🟢 [Weights](https://play.forum.ircam.fr/rave-vst-api/get_model/musicnet) | CNN |

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

| Model and resources | Architecture |
| --- | --- |
| **FM-Singer** · [Paper](https://arxiv.org/abs/2601.00217) · [Code](https://github.com/alsgur9368/FM-Singer) · 🟢 [Weights](https://github.com/alsgur9368/FM-Singer) | CNN |
| **CSSinger** · [Paper](https://arxiv.org/abs/2412.08918) · Code — · ⚪ Weights — | CNN |
| **So-VITS-SVC 4.x** · Paper — · [Code](https://github.com/RVC-Boss/sovits) · 🟢 [Weights](https://github.com/RVC-Boss/sovits) | CNN |
| **UniSyn** · [Paper](https://arxiv.org/abs/2212.01546) · Code — · ⚪ Weights — | CNN |
| **VISinger 2** · [Paper](https://arxiv.org/abs/2211.02903) · Code — · ⚪ Weights — | CNN |
| **VISinger** · [Paper](https://arxiv.org/abs/2110.08813) · Code — · ⚪ Weights — | CNN |

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

| Model and resources | Architecture |
| --- | --- |
| **dots.tts AudioVAE** · [Paper](https://arxiv.org/abs/2606.07080) · [Code](https://github.com/studio-dots-ai/dots.tts) · 🟡 [Weights](https://huggingface.co/rednote-hilab/dots.tts-base) | CNN |
| **VoxCPM2 AudioVAE** · [Paper](https://arxiv.org/abs/2606.06928) · [Code](https://github.com/OpenBMB/VoxCPM) · 🟡 [Weights](https://huggingface.co/openbmb/VoxCPM2) | CNN |
| **HoliTok** · [Paper](https://arxiv.org/abs/2605.29948) · [Code](https://github.com/bovod-sjtu/HoliTok) · 🟡 [Weights](https://github.com/bovod-sjtu/HoliTok) | CNN |
| **LongCat Wav-VAE** · [Paper](https://arxiv.org/abs/2603.29339) · [Code](https://github.com/meituan-longcat/LongCat-AudioDiT) · 🟡 [Weights](https://huggingface.co/meituan-longcat/LongCat-AudioDiT-3.5B) | CNN |
| **MingTok-Audio** · [Paper](https://arxiv.org/abs/2511.05516) · [Code](https://github.com/inclusionAI/Ming-UniAudio) · 🟢 [Weights](https://huggingface.co/inclusionAI/MingTok-Audio) | Transformer |
| **SALAD-VAE** · [Paper](https://arxiv.org/abs/2510.07592) · Code — · ⚪ Weights — | CNN |
| **Semantic-VAE** · [Paper](https://arxiv.org/abs/2509.22167) · [Code](https://github.com/ZhikangNiu/Semantic-VAE) · 🟢 [Weights](https://huggingface.co/zkniu/Semantic-VAE) | CNN |
| **Semantic-VAE-600k** · [Paper](https://arxiv.org/abs/2509.22167) · [Code](https://github.com/ZhikangNiu/Semantic-VAE) · ⚪ Weights — | CNN |
| **Semantic-VAE-A16** · [Paper](https://arxiv.org/abs/2509.22167) · [Code](https://github.com/ZhikangNiu/Semantic-VAE) · 🟢 [Weights](https://huggingface.co/zkniu/Semantic-VAE/tree/main/acoustic_vae_dim16) | CNN |
| **Semantic-VAE-A64** · [Paper](https://arxiv.org/abs/2509.22167) · [Code](https://github.com/ZhikangNiu/Semantic-VAE) · 🟢 [Weights](https://huggingface.co/zkniu/Semantic-VAE/tree/main/acoustic_vae_dim64) | CNN |
| **VoxCPM AudioVAE** · [Paper](https://arxiv.org/abs/2509.24650) · [Code](https://github.com/OpenBMB/VoxCPM) · 🟢 [Weights](https://huggingface.co/openbmb/VoxCPM-0.5B/blob/main/audiovae.pth) | CNN |
| **VibeVoice Acoustic Tokenizer** · [Paper](https://arxiv.org/abs/2508.19205) · [Code](https://github.com/microsoft/VibeVoice) · 🟢 [Weights](https://huggingface.co/microsoft/VibeVoice-AcousticTokenizer) | CNN |

<p align="right"><a href="#top">↑ Back to top</a></p>
