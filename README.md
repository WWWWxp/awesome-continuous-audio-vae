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
- **Feature**: acoustic representation encoded by the VAE, such as waveform, mel spectrogram, or complex STFT.
- **Architecture**: coarse encoder/decoder backbone family.
- **Weights**: 🟢 standalone component · 🟡 bundled in a larger checkpoint; absent links are omitted.
- **N/R**: not reported in the linked paper, code, or checkpoint configuration.

<a id="audio"></a>
## 🔊 Audio / Sound

General audio, environmental sound, Foley, and multi-domain reconstruction. **25 models · 16 with weights.**

| Model and resources | Year–Month | Sample rate | Frame rate | Dim | Feature | Architecture |
| --- | ---: | ---: | ---: | ---: | --- | --- |
| **OmniVAE audio-only** · [Paper](https://arxiv.org/abs/2607.23855) · [Code](https://github.com/OpenMOSS/OmniVAE) · 🟢 [Weights](https://huggingface.co/OpenMOSS-Team/OmniVAE) | 2026-07 | 48 kHz | 50 Hz | 128 | waveform | CNN |
| **Qwen-Audio-3 Shared VAE** · [Paper](https://arxiv.org/abs/2607.27011) | 2026-07 | 48 kHz | 25 Hz | 128 | stereo waveform | CNN |
| **Qwen-Audio-VAE** · [Paper](https://arxiv.org/abs/2607.11738) | 2026-07 | 24 kHz | 12.5 Hz | 128 | waveform | CNN + Transformer |
| **AudioCALM Audio VAE** · [Paper](https://arxiv.org/abs/2606.23080) | 2026-06 | 44.1 kHz | ≈10.75 Hz | 64 | stereo waveform | CNN + Transformer |
| **KVAE-Audio** · [Code](https://github.com/kandinskylab/kvae-audio) · 🟢 [Weights](https://huggingface.co/kandinskylab/KVAE-Audio) | 2026-06 | 48 kHz | 50 Hz | 64 | waveform | CNN |
| **STAR-VAE** · [Paper](https://arxiv.org/abs/2606.23064) | 2026-06 | N/R | N/R | N/R | waveform | N/R |
| **UniSonate Mel-VAE** · [Paper](https://arxiv.org/abs/2604.22209) | 2026-04 | 44.1 kHz | 43 Hz | 40 | mel spectrogram | CNN |
| **GenAE** · [Paper](https://arxiv.org/abs/2602.15749) | 2026-02 | 44.1 kHz | 13.125 Hz | N/R | multichannel waveform | CNN + Transformer |
| **Ming-omni-tts continuous tokenizer** · [Code](https://github.com/inclusionAI/Ming-omni-tts) · 🟢 [Weights](https://huggingface.co/inclusionAI/Ming-omni-tts-tokenizer-12Hz) | 2026-02 | 44.1 kHz | 12.5 Hz | 64 | waveform | Transformer |
| **LTX-2 Audio VAE** · [Code](https://github.com/Lightricks/LTX-2) · 🟢 [Weights](https://huggingface.co/Lightricks/LTX-2) | 2026-01 | 16 kHz | 25 Hz | 128 | mel spectrogram | CNN |
| **Omni2Sound OOB/Wav VAE** · [Paper](https://arxiv.org/abs/2601.02731) · [Code](https://github.com/omni2sound/Omni2Sound) · 🟢 [Weights](https://huggingface.co/Dalision/Omni2Sound) | 2026-01 | 16 kHz | 25 Hz | 64 | waveform | CNN |
| **HunyuanVideo-Foley Audio VAE** · [Paper](https://arxiv.org/abs/2508.16930) · [Code](https://github.com/Tencent-Hunyuan/HunyuanVideo-Foley) · 🟢 [Weights](https://huggingface.co/tencent/HunyuanVideo-Foley) | 2025-08 | 48 kHz | 50 Hz | 128 | waveform | CNN |
| **Kling-Foley Mel-VAE** · [Paper](https://arxiv.org/abs/2506.19774) | 2025-06 | 44.1 kHz | 43 Hz | 40 | mel spectrogram | CNN |
| **MMAudio VAE 16 kHz** · [Paper](https://arxiv.org/abs/2412.15322) · [Code](https://github.com/hkchengrex/MMAudio) · 🟢 [Weights](https://huggingface.co/hkchengrex/MMAudio) | 2024-12 | 16 kHz | 31.25 Hz | 20 | mel spectrogram | CNN |
| **MMAudio VAE 44.1 kHz** · [Paper](https://arxiv.org/abs/2412.15322) · [Code](https://github.com/hkchengrex/MMAudio) · 🟢 [Weights](https://huggingface.co/hkchengrex/MMAudio) | 2024-12 | 44.1 kHz | 43.07 Hz | 40 | mel spectrogram | CNN |
| **MultiFoley DAC-VAE** · [Paper](https://arxiv.org/abs/2411.17698) | 2024-11 | 48 kHz | 40 Hz | 64 | waveform | CNN |
| **DACVAE / Movie Gen Audio Autoencoder** · [Paper](https://arxiv.org/abs/2410.13720) · [Code](https://github.com/facebookresearch/dacvae) · 🟢 [Weights](https://huggingface.co/facebook/dacvae-watermarked) | 2024-10 | 48 kHz | 25 Hz | 128 | waveform | CNN |
| **EzAudio 1-D VAE** · [Paper](https://arxiv.org/abs/2409.10819) · [Code](https://github.com/haidog-yaqub/EzAudio) · 🟡 [Weights](https://github.com/haidog-yaqub/EzAudio) | 2024-09 | 24 kHz | 50 Hz | 128 | waveform | CNN |
| **StableAudio1.0 / Stable Audio Open VAE** · [Paper](https://arxiv.org/abs/2407.14358) · [Code](https://github.com/Stability-AI/stable-audio-tools) · 🟡 [Weights](https://huggingface.co/stabilityai/stable-audio-open-1.0) | 2024-07 | 44.1 kHz | 21.5 Hz | 64 | waveform | CNN |
| **Wave-VAE (Stability AI)** · [Code](https://github.com/Stability-AI/stable-audio-tools) | 2024-07 | 44.1 kHz | 21 Hz | 64 | waveform | N/R |
| **Auffusion VAE** · [Paper](https://arxiv.org/abs/2401.01044) · [Code](https://github.com/happylittlecat2333/Auffusion) · 🟡 [Weights](https://huggingface.co/auffusion/auffusion) | 2024-01 | 16 kHz | 12.5 Hz | 128 | mel-spectrogram image | CNN |
| **AudioLDM 2 VAE** · [Paper](https://arxiv.org/abs/2308.05734) · [Code](https://github.com/haoheliu/AudioLDM2) · 🟢 [Weights](https://huggingface.co/cvssp/audioldm2/tree/main/vae) | 2023-08 | 16 kHz | 25 Hz | 128 | mel spectrogram | CNN |
| **Make-An-Audio 2 Audio VAE** · [Paper](https://arxiv.org/abs/2305.18474) · [Code](https://github.com/bytedance/Make-An-Audio-2) · 🟡 [Weights](https://huggingface.co/ByteDance/Make-An-Audio-2) | 2023-05 | 16 kHz | 31.25 Hz | 20 | mel spectrogram | CNN + Transformer |
| **AudioLDM VAE** · [Paper](https://arxiv.org/abs/2301.12503) · [Code](https://github.com/haoheliu/AudioLDM) · 🟡 [Weights](https://huggingface.co/cvssp/audioldm-s-full-v2) | 2023-01 | 16 kHz | 25 Hz | 128 | mel spectrogram | CNN |
| **Make-An-Audio VAE** · [Paper](https://arxiv.org/abs/2301.12661) · [Code](https://github.com/Text-to-Audio/Make-An-Audio) · 🟡 [Weights](https://github.com/Text-to-Audio/Make-An-Audio) | 2023-01 | 16 kHz | 7.8 Hz | 40 | mel spectrogram | CNN |

<p align="right"><a href="#top">↑ Back to top</a></p>

<a id="music"></a>
## 🎵 Music

Autoencoders designed for music generation and representation. **13 models · 10 with weights.**

| Model and resources | Year–Month | Sample rate | Frame rate | Dim | Feature | Architecture |
| --- | ---: | ---: | ---: | ---: | --- | --- |
| **SAME-L** · [Paper](https://arxiv.org/abs/2605.18613) · [Code](https://github.com/Stability-AI/stable-audio-3) · 🟢 [Weights](https://huggingface.co/stabilityai/SAME-L) | 2026-05 | 44.1 kHz | 10.77 Hz | 256 | waveform | Transformer |
| **SAME-S** · [Paper](https://arxiv.org/abs/2605.18613) · [Code](https://github.com/Stability-AI/stable-audio-3) · 🟢 [Weights](https://huggingface.co/stabilityai/SAME-S) | 2026-05 | 44.1 kHz | 10.77 Hz | 256 | waveform | Transformer |
| **ACE-Step 1.5 VAE** · [Paper](https://arxiv.org/abs/2602.00744) · [Code](https://github.com/ace-step/ACE-Step-1.5) · 🟡 [Weights](https://huggingface.co/ACE-Step/Ace-Step1.5) | 2026-02 | 48 kHz | 25 Hz | 64 | waveform | CNN |
| **DiffRhythm 2 Music VAE** · [Paper](https://arxiv.org/abs/2510.22950) · [Code](https://github.com/ASLP-lab/DiffRhythm) | 2025-10 | 24 kHz | 5 Hz | 64 | waveform | CNN + Transformer |
| **CoDiCodec continuous branch** · [Paper](https://arxiv.org/abs/2509.09836) · [Code](https://github.com/SonyCSLParis/codicodec) · 🟢 [Weights](https://pypi.org/project/codicodec/) | 2025-09 | 44.1 kHz | 10.77 Hz | 64 | complex STFT | CNN + Transformer |
| **epsilonar-VAE** · [Paper](https://arxiv.org/abs/2509.14912) · [Code](https://huggingface.co/earlab/EAR_VAE) | 2025-09 | 44.1 kHz | 43 Hz | N/R | stereo waveform | CNN + Transformer |
| **ACE-Step DCAE** · [Paper](https://arxiv.org/abs/2506.00045) · [Code](https://github.com/ace-step/ACE-Step) · 🟡 [Weights](https://huggingface.co/ACE-Step/ACE-Step-v1-3.5B) | 2025-06 | 32 kHz | 10.77 Hz | 128 | mel spectrogram | CNN |
| **DiffRhythm VAE** · [Paper](https://arxiv.org/abs/2503.01183) · [Code](https://github.com/ASLP-lab/DiffRhythm) · 🟢 [Weights](https://huggingface.co/ASLP-lab/DiffRhythm-vae) | 2025-03 | 44.1 kHz | 21.53 Hz | 64 | waveform | CNN |
| **Music2Latent** · [Paper](https://arxiv.org/abs/2408.06500) · [Code](https://github.com/SonyCSLParis/music2latent) · 🟢 [Weights](https://huggingface.co/SonyCSLParis/music2latent) | 2024-08 | 44.1 kHz | 10.77 Hz | 64 | complex STFT | CNN + Transformer |
| **Descript Audio VAE (community)** · [Code](https://github.com/innnky/descript-audio-vae) · 🟢 [Weights](https://github.com/innnky/descript-audio-vae) | 2024-01 | 44.1 kHz | 86.13 Hz | 128 | waveform | CNN |
| **Moûsai Diffusion Autoencoder** · [Paper](https://arxiv.org/abs/2301.11757) · [Code](https://github.com/archinetai/audio-diffusion-pytorch) | 2023-01 | 48 kHz | N/R | 32 | magnitude spectrogram | CNN |
| **Musika autoencoder** · [Paper](https://arxiv.org/abs/2208.08706) · [Code](https://github.com/marcoppasini/musika) · 🟢 [Weights](https://huggingface.co/marcop/musika_ae) | 2022-08 | 22.05 kHz | 11.89 / 23.78 Hz | 32 / 64 | magnitude spectrogram | CNN |
| **RAVE v2 (MusicNet)** · [Paper](https://arxiv.org/abs/2111.05011) · [Code](https://github.com/acids-ircam/rave) · 🟢 [Weights](https://play.forum.ircam.fr/rave-vst-api/get_model/musicnet) | 2021-11 | 44.1 kHz | 21.53 Hz | 16 | waveform | CNN |

<p align="right"><a href="#top">↑ Back to top</a></p>

<a id="singing"></a>
## 🎤 Singing

Singing reconstruction, singing voice synthesis, and voice conversion. **6 models · 2 with weights.**

| Model and resources | Year–Month | Sample rate | Frame rate | Dim | Feature | Architecture |
| --- | ---: | ---: | ---: | ---: | --- | --- |
| **FM-Singer** · [Paper](https://arxiv.org/abs/2601.00217) · [Code](https://github.com/alsgur9368/FM-Singer) · 🟢 [Weights](https://github.com/alsgur9368/FM-Singer) | 2026-01 | 44.1 kHz | 86.13 Hz | 192 | score/lyrics + waveform | CNN |
| **CSSinger** · [Paper](https://arxiv.org/abs/2412.08918) | 2024-12 | 44.1 kHz | 86.13 Hz | 192 | score/lyrics + waveform | CNN |
| **So-VITS-SVC 4.x** · [Code](https://github.com/RVC-Boss/sovits) · 🟢 [Weights](https://github.com/RVC-Boss/sovits) | 2023-05 | 44.1 kHz | 86.13 Hz | 192 | content/F0 + waveform | CNN |
| **UniSyn** · [Paper](https://arxiv.org/abs/2212.01546) | 2022-12 | 24 kHz | 80 Hz | N/R | score/lyrics + waveform | CNN |
| **VISinger 2** · [Paper](https://arxiv.org/abs/2211.02903) | 2022-11 | 44.1 kHz | N/R | 192 | score/lyrics + waveform | CNN |
| **VISinger** · [Paper](https://arxiv.org/abs/2110.08813) | 2021-10 | 24 kHz | N/R | N/R | score/lyrics + waveform | CNN |

<p align="right"><a href="#top">↑ Back to top</a></p>

<a id="speech"></a>
## 🗣️ Speech

Speech reconstruction and conditional text-to-speech VAEs. **12 models · 10 with weights.**

| Model and resources | Year–Month | Sample rate | Frame rate | Dim | Feature | Architecture |
| --- | ---: | ---: | ---: | ---: | --- | --- |
| **dots.tts AudioVAE** · [Paper](https://arxiv.org/abs/2606.07080) · [Code](https://github.com/studio-dots-ai/dots.tts) · 🟡 [Weights](https://huggingface.co/rednote-hilab/dots.tts-base) | 2026-06 | 48 kHz | 25 Hz | 128 | waveform | CNN |
| **VoxCPM2 AudioVAE** · [Paper](https://arxiv.org/abs/2606.06928) · [Code](https://github.com/OpenBMB/VoxCPM) · 🟡 [Weights](https://huggingface.co/openbmb/VoxCPM2) | 2026-06 | 16 kHz | 25 Hz | 64 | waveform | CNN |
| **HoliTok** · [Paper](https://arxiv.org/abs/2605.29948) · [Code](https://github.com/bovod-sjtu/HoliTok) · 🟡 [Weights](https://github.com/bovod-sjtu/HoliTok) | 2026-05 | 48 kHz | 25 Hz | 128 | waveform | CNN |
| **LongCat Wav-VAE** · [Paper](https://arxiv.org/abs/2603.29339) · [Code](https://github.com/meituan-longcat/LongCat-AudioDiT) · 🟡 [Weights](https://huggingface.co/meituan-longcat/LongCat-AudioDiT-3.5B) | 2026-03 | 24 kHz | 11.72 Hz | 64 | waveform | CNN |
| **MingTok-Audio** · [Paper](https://arxiv.org/abs/2511.05516) · [Code](https://github.com/inclusionAI/Ming-UniAudio) · 🟢 [Weights](https://huggingface.co/inclusionAI/MingTok-Audio) | 2025-11 | 16 kHz | 50 Hz | 64 | waveform | Transformer |
| **SALAD-VAE** · [Paper](https://arxiv.org/abs/2510.07592) | 2025-10 | N/R | 7.8 Hz | 64 / 128 | complex STFT | CNN |
| **Semantic-VAE** · [Paper](https://arxiv.org/abs/2509.22167) · [Code](https://github.com/ZhikangNiu/Semantic-VAE) · 🟢 [Weights](https://huggingface.co/zkniu/Semantic-VAE) | 2025-09 | 16 kHz | 40 Hz | 64 | condition + waveform | CNN |
| **Semantic-VAE-600k** · [Paper](https://arxiv.org/abs/2509.22167) · [Code](https://github.com/ZhikangNiu/Semantic-VAE) | 2025-09 | 16 kHz | 40 Hz | 64 | condition + waveform | CNN |
| **Semantic-VAE-A16** · [Paper](https://arxiv.org/abs/2509.22167) · [Code](https://github.com/ZhikangNiu/Semantic-VAE) · 🟢 [Weights](https://huggingface.co/zkniu/Semantic-VAE/tree/main/acoustic_vae_dim16) | 2025-09 | 16 kHz | 40 Hz | 16 | condition + waveform | CNN |
| **Semantic-VAE-A64** · [Paper](https://arxiv.org/abs/2509.22167) · [Code](https://github.com/ZhikangNiu/Semantic-VAE) · 🟢 [Weights](https://huggingface.co/zkniu/Semantic-VAE/tree/main/acoustic_vae_dim64) | 2025-09 | 16 kHz | 40 Hz | 64 | condition + waveform | CNN |
| **VoxCPM AudioVAE** · [Paper](https://arxiv.org/abs/2509.24650) · [Code](https://github.com/OpenBMB/VoxCPM) · 🟢 [Weights](https://huggingface.co/openbmb/VoxCPM-0.5B/blob/main/audiovae.pth) | 2025-09 | 16 kHz | 25 Hz | 64 | waveform | CNN |
| **VibeVoice Acoustic Tokenizer** · [Paper](https://arxiv.org/abs/2508.19205) · [Code](https://github.com/microsoft/VibeVoice) · 🟢 [Weights](https://huggingface.co/microsoft/VibeVoice-AcousticTokenizer) | 2025-08 | 24 kHz | 7.5 Hz | 64 | waveform | CNN |

<p align="right"><a href="#top">↑ Back to top</a></p>
