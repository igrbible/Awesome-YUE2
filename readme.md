# Awesome YUE2 [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> Open music generation model by M-A-P that writes full songs with vocals from a style prompt and lyrics, planning each song as a score before it renders the audio.

YuE2 is the second generation of [YuE](https://github.com/multimodal-art-projection/YuE/tree/YuE-v1): an autoregressive planner writes an ABC score and the music tokens, and a second stage renders them as 48 kHz stereo. This list collects the official releases and the community work around them: inference engines, studios, ComfyUI nodes, fine-tunes, LoRAs, decoders, tools, datasets and guides.

The official resources come first in their section; everything else is sorted alphabetically. The YuE2 weights are released under CC BY-NC 4.0 with an additional permission for individual creators, and most community weights inherit that licence, so read the [model licence](https://github.com/multimodal-art-projection/YuE/blob/main/MODEL_LICENSE) before you publish songs made with them.

## Contents

- [Official](#official)
- [Papers](#papers)
- [Inference Engines and Ports](#inference-engines-and-ports)
- [Studios and Apps](#studios-and-apps)
- [Apple Silicon](#apple-silicon)
- [DAW and Mobile](#daw-and-mobile)
- [ComfyUI](#comfyui)
- [Installers and Launchers](#installers-and-launchers)
- [Fine-Tunes and Merges](#fine-tunes-and-merges)
- [LoRAs and Adapters](#loras-and-adapters)
- [VAEs and Decoders](#vaes-and-decoders)
- [Converted and Quantized Weights](#converted-and-quantized-weights)
- [Training](#training)
- [Transcription and Scores](#transcription-and-scores)
- [Datasets and Benchmarks](#datasets-and-benchmarks)
- [Online Demos](#online-demos)
- [Guides](#guides)

## Official

- [YuE2](https://github.com/multimodal-art-projection/YuE) - Official code, inference package, agent skill and documentation from M-A-P (code under Apache 2.0).
- [YuE2-3B](https://huggingface.co/m-a-p/YuE2-3B) - The official model weights on Hugging Face.
- [Project Page](https://map-yue2.github.io/) - Listening examples, demos and interactive results for YuE2, MERT2 and SheetSage2.
- [Discord](https://discord.gg/ssAyWMnMzu) - The official community server of the YuE2 authors.

## Papers

- [MERT: Acoustic Music Understanding Model with Large-Scale Self-supervised Training](https://arxiv.org/abs/2306.00107) - The music encoder family behind MERT2, which SheetSage2 uses as its encoder (2023).
- [SheetSage2: Coherent Lead-Sheet Transcription with Synthetic Supervision](https://arxiv.org/abs/2610.05336) - The transcription model that writes the lead sheets YuE2 covers and score edits start from (2026).
- [YuE: Scaling Open Foundation Models for Long-Form Music Generation](https://arxiv.org/abs/2503.08638) - The first-generation YuE models (2025).
- [YuE2: Unifying Symbolic and Audio Music Generation at Frontier Quality](https://arxiv.org/abs/2609.33757) - The YuE2 technical report: model, training, listening tests, score editing and zero-shot covers (2026).
- [YuE2-VAE-RS ×3: A Grown Decoder for the YuE2 Music VAE](https://doi.org/10.5281/zenodo.24167962) - Technical report on a drop-in replacement decoder for YuE2-Vae, on Zenodo under CC BY 4.0 (2026). Written by this list's maintainers.

## Inference Engines and Ports

- [audio.cpp](https://github.com/0xShug0/audio.cpp) - All-in-one C++/ggml inference engine for audio models, with YuE2 and SheetSage2, LoRA adapters and a web UI.
- [HOT-Step CPP](https://github.com/scragnog/HOT-Step-CPP) - Local C++/GGML music generation engine and app that runs YuE2 among other models.
- [mlx-Yue](https://github.com/vanch007/mlx-Yue) - Native Apple Silicon (MLX) port of YuE2-3B generation and audio transcription.
- [YuE2 Modular Diffusers](https://huggingface.co/OzzyGT/YuE2-Modular) - Modular Diffusers blocks for YuE2, with the weights in Diffusers layout in a companion repository.
- [yue2.cpp](https://github.com/ServeurpersoCom/yue2.cpp) - Portable C++17/GGML implementation: style and lyrics in, stereo 48 kHz out, on CPU, CUDA, ROCm, Metal and Vulkan.
- [yue2.cpp (engival)](https://github.com/engival/yue2.cpp) - Single-binary YuE2 on ggml and Vulkan with an EAGLE-3 draft head for speculative decoding.
- [yue2-fp16-turing](https://github.com/loktar00/yue2-fp16-turing) - YuE2 patched to run in fp16 on RTX 20-series (Turing) GPUs, with a web UI and an API.
- [YuE2-Turbo](https://github.com/NoizAI/YuE2-Turbo) - NOIZ's inference and serving toolkit: the same model and recipe, faster per song, with concurrent requests.

## Studios and Apps

- [ds-yue-webui](https://github.com/DocShotgun/ds-yue-webui) - Web UI for song generation, covers and editing.
- [GoKuk](https://github.com/Garionhk/GoKuk) - Portable Windows app for NVIDIA GPUs with songs from style and lyrics, covers from a recording and a piano-roll score editor.
- [Lux in Music](https://github.com/lvxworld/lux-in-music) - Local studio on audio.cpp with stem separation and section editing.
- [Maestro](https://github.com/Blizaine/Maestro) - Local video, image and music studio that includes YuE2 for songs, composition planning and covers.
- [OpenSuno-YuE2](https://github.com/victorcampeanu/OpenSuno-YuE2) - Local studio for Apple Silicon and Windows with NVIDIA, with automatic model downloads.
- [Remiqora](https://github.com/inikolax/remiqora) - Local music studio with YuE2-3B and ACE-Step 1.5, stem separation and an AI arranger that adds parts to a track.
- [Ruach Studio](https://github.com/igrbible/Ruach_Studio) - Self-hosted studio on yue2.cpp with an editable score, a lyrics writer, a refiner with a piano roll, a LoRA trainer and a song library. Made by this list's maintainers.
- [yeufonic](https://github.com/yeufonic/yeufonic) - Web interface for covers, songs from a prompt, score editing, stem extraction and LoRA creation.
- [YuE2 Studio (krakenunbound)](https://github.com/krakenunbound/yue2-studio) - Native Windows app with a song library, lyric sync, covers, stem separation and video tools.
- [YuE2 Studio (timoncool)](https://github.com/timoncool/YuE2-Studio) - Native Windows app with an editable score, covers and exact replay of earlier takes.
- [YuE2 Studio (vrgamegirl19)](https://github.com/vrgamegirl19/Yue2_Studio) - Local web studio in beta with covers, an LLM writing room, song batches and experimental LoRA training.
- [YuE2-Radio](https://github.com/PasiKoodaa/YuE2-Radio) - Local AI radio: a language model in LM Studio writes the lyrics and YuE2 on audio.cpp sings them, station by station.

## Apple Silicon

- [YuE Studio](https://github.com/tonywestonuk/YuE-Studio) - Native Mac app tuned for Apple Silicon, using the GPU and the Neural Engine.
- [YUE2 // GROOVE](https://github.com/deadjoe/yue2_groove) - Unofficial web UI, Apple Silicon first, with Linux and CUDA through the official package.
- [YuE2 Studio (ianiv)](https://github.com/ianiv/YuE2) - Local web app for YuE2-3B on MLX.
- [YuE2Mac](https://github.com/arinltte/YuE2Mac) - Native macOS songwriting app running YuE2 at 8-bit on the Apple GPU through MLX.
- [yue2-studio (stavitian)](https://github.com/stavitian/yue2-studio) - macOS app and installer on MLX for generation, covers and transcription, with fixes for 24 GB Macs.

## DAW and Mobile

- [gary4juce](https://github.com/betweentwomidnights/gary4juce) - DAW plug-in that brings open music models, YuE2 among them, into the session as audio and MIDI.
- [killa-yue](https://github.com/JackKnifeAI/killa-yue) - Open-source music studio for Android phones with full songs, lyric writing, stem splitting and a mixer.
- [Plenio VST3](https://github.com/jplenio/Plenio-VST3) - VST3 and ARA 2 plug-in that drives Plenio for ComfyUI from inside a DAW.
- [SoundCraft Plenio](https://github.com/jplenio/soundcraft-plenio) - Open-source Rust DAW with a Plenio add-in for YuE2 songs and covers on tracks.

## ComfyUI

- [Native YuE2 Workflow](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/audio_yue2_text2music.json) - The official ComfyUI text-to-music template for the built-in YuE2 nodes.
- [ComfyUI-FL-YuE2](https://github.com/filliptm/ComfyUI-FL-YuE2) - YuE2 generation nodes with an editable piano roll.
- [ComfyUI-FS_Audio_Suite](https://github.com/KytraScript/ComfyUI-FS_Audio_Suite) - Modular YuE2 nodes that need no stock nodes, starting with hum-to-song.
- [ComfyUI-Olm-YuE2](https://github.com/o-l-l-i/ComfyUI-Olm-YuE2) - Songs from style and lyrics with optional score viewing and editing and separate generation stages.
- [ComfyUI-SongScribe](https://github.com/TheLocalLab/ComfyUI-SongScribe) - Prompt nodes with 73 style presets and song analysis for YuE2 and MiniMax Music 3, on CPU.
- [ComfyUI_YuE](https://github.com/smthemex/ComfyUI_YuE) - Long-standing YuE node pack, updated for YuE2.
- [ComfyUI-YuE2 (endman100)](https://github.com/endman100/ComfyUI-YuE2) - Composable nodes for the ComfyUI V3 node API.
- [ComfyUI-YuE2 (nvmax)](https://github.com/nvmax/ComfyUI-YuE2) - In-process node suite on ComfyUI's native YuE2 acceleration, with an LM Studio co-producer.
- [ComfyUI-YuE2 (piscesbody)](https://github.com/piscesbody/ComfyUI-YuE2) - Generation and SheetSage2 transcription in one pack, chained into a full cover pipeline.
- [ComfyUI-YuE2 (ScryptHunter)](https://github.com/ScryptHunter/ComfyUI-YuE2) - Dependency-safe fork of the piscesbody pack for current ComfyUI and Transformers.
- [Comfyui-YuE2-T8](https://github.com/T8mars/Comfyui-YuE2-T8) - Bilingual node pack with a one-click Windows bundle and its own model repository.
- [Plenio Music Production System](https://github.com/jplenio/Plenio-Music-Production-System) - ComfyUI extension that takes a song or cover from a brief to a mastered track, with a notation editor and a player.
- [YuE2-ComfyUI](https://github.com/pytraveler/YuE2-ComfyUI) - Nodes with a piano-roll score editor, Edit Track (retake, cut, move or extend parts of a song) and covers from audio or MIDI.

## Installers and Launchers

- [yue2-colab-studio](https://github.com/Openclaw-Metis/yue2-colab-studio) - Unofficial Gradio studio for running YuE2 on a Google Colab L4.
- [yue2-groove-pinokio](https://github.com/deadjoe/yue2-groove-pinokio) - Pinokio launcher for YUE2 // GROOVE.
- [yue2-kit](https://github.com/IronWolve/yue2-kit) - Install kit on yue2.cpp with a studio page, LoRAs and VAEs.
- [yue2-mlx.pinokio](https://github.com/Rdx-ai-art/yue2-mlx.pinokio) - Mac-only Pinokio app with native MLX inference.

## Fine-Tunes and Merges

- [YuE2-3B-Ruach_Studio-IRA-Merge](https://huggingface.co/goldhub/YuE2-3B-Ruach_Studio-IRA-Merge) - YuE2-3B with two community LoRAs folded into the weights (Instrumental and Real Audio by Mothersuperior), plus variants that also fold in monsterovich's epic-trailer and industrial-rock adapters. Made by this list's maintainers.
- [YuE2-RS-Finetunes](https://huggingface.co/goldhub/YuE2-RS-Finetunes) - Full fine-tunes of both halves of YuE2-3B on about 1,800 hours of music, released as merges in GGUF, safetensors and ComfyUI formats. Made by this list's maintainers.

## LoRAs and Adapters

- [Ruach Studio LoRAs](https://huggingface.co/goldhub/Ruach_Studio_LoRAs) - Adapters for instruments YuE2 plays weakly or not at all, such as the shofar and the duduk, and for voice types. Made by this list's maintainers.
- [yue2-1980s-eurodisco-lora](https://huggingface.co/jamespetts/yue2-1980s-eurodisco-lora) - CC0 renderer adapter for 1980s Eurodisco production.
- [yue2-1980s-italo-disco-lora](https://huggingface.co/jamespetts/yue2-1980s-italo-disco-lora) - CC0 renderer adapter for Italo disco, trained only on CC0 songs.
- [yue2-1980s-two-tone-ska-lora](https://huggingface.co/jamespetts/yue2-1980s-two-tone-ska-lora) - CC0 renderer adapter for early-1980s British two-tone ska.
- [yue2-cnzn-canzone-italiana](https://huggingface.co/becausereasons/yue2-cnzn-canzone-italiana) - Style LoRAs for classic Italian pop with vocals in Italian.
- [yue2-concept-sliders](https://github.com/mikkel/yue2-concept-sliders) - Code for 16 native music concept sliders with routed particles and ComfyUI support.
- [YuE2-hum-to-song](https://huggingface.co/Mothersuperior/YuE2-hum-to-song) - Hum 10 to 30 seconds, add a style and lyrics, and get a song that keeps your melody.
- [yue2-industrial-rock-lora](https://huggingface.co/monsterovich/yue2-industrial-rock-lora) - Planner and renderer adapters for industrial rock.
- [YuE2-instrumental-cot-full-loras](https://huggingface.co/Mothersuperior/YuE2-instrumental-cot-full-loras) - Planner LoRA for instrumental music with a section plan.
- [yue2-mltnt-militant-reggae](https://huggingface.co/becausereasons/yue2-mltnt-militant-reggae) - Style LoRAs for modern militant roots reggae that patch both halves of the model.
- [yue2-particle-sliders](https://huggingface.co/ntc-ai/yue2-particle-sliders) - Weights for 16 voice and genre sliders, with distilled standard LoRAs.
- [yue2-steps-from-hell](https://huggingface.co/monsterovich/yue2-steps-from-hell) - Planner and renderer adapters for epic cinematic trailer music.

## VAEs and Decoders

- [YuE2-Vae](https://huggingface.co/m-a-p/YuE2-Vae) - The official audio VAE that turns the latents into 48 kHz stereo.
- [YuE2-Vae-legacy](https://huggingface.co/m-a-p/YuE2-Vae-legacy) - The earlier official decoder release, with the same encoder and architecture.
- [YuE2-Vae-merge-0.666](https://huggingface.co/Mothersuperior/YuE2-Vae-merge-0.666) - Linear weight merge of the two official decoders (0.666 and 0.334).
- [YuE2-VAE-RS-x3](https://huggingface.co/goldhub/YuE2-VAE-RS-x3) - Drop-in decoder for YuE2-Vae (the same latents in, the same 48 kHz stereo out) trained to lower its 100 Hz ripple and its 6 and 12 kHz seams, float32. Made by this list's maintainers.

## Converted and Quantized Weights

- [audio-cpp/Yue2-3B-GGUF](https://huggingface.co/audio-cpp/Yue2-3B-GGUF) - GGUF weights for audio.cpp in BF16, Q8_0 and Q4_0, with comparison samples.
- [Comfy-Org/YuE2](https://huggingface.co/Comfy-Org/YuE2) - YuE2-3B and SheetSage2 repackaged for the native ComfyUI nodes.
- [mlx-community/YuE2-3B-bf16](https://huggingface.co/mlx-community/YuE2-3B-bf16) - YuE2-3B converted to MLX in bf16.
- [scragnog/YuE2-GGUF](https://huggingface.co/scragnog/YuE2-GGUF) - GGUF conversions of the model and the VAE for HOT-Step CPP.
- [Serveurperso/YuE2-GGUF](https://huggingface.co/Serveurperso/YuE2-GGUF) - Pre-quantized GGUF models for yue2.cpp, including SheetSage2 and MERT2.
- [WaveCut/YuE2-3B-OrbitQuant-W4A4](https://huggingface.co/WaveCut/YuE2-3B-OrbitQuant-W4A4) - Transformer weights and activations packed to 4 bits, about 3 GB instead of 7.3 GB.

## Training

- [AcademiaSD LoRAlab Trainer Studio](https://github.com/AcademiaSD/AcademiaSD_LoRAlab-TrainerStudio) - LoRA trainer for many image and audio models, YuE2-3B among them, on consumer NVIDIA GPUs.
- [AI Toolkit](https://github.com/ostris/ai-toolkit) - Fine-tuning toolkit that trains YuE2-3B LoRAs with the community audio tokenizer.
- [ComfyUI-YuE2-Trainer](https://github.com/Starnodes2024/ComfyUI-YuE2-Trainer) - Experimental LoRA training nodes for ComfyUI.
- [yue2-lora-training](https://github.com/directedbykobyperez/yue2-lora-training) - Train artist LoRAs from your own songs: upload, caption, train and listen.
- [yue2-mothersuperior-realaudio-tokenizer-v4](https://huggingface.co/Mothersuperior/yue2-mothersuperior-realaudio-tokenizer-v4) - The audio-to-token encoder YuE2 does not ship, with a renderer LoRA for real-production sound; most community trainers build on it.

## Transcription and Scores

- [SheetSage2](https://huggingface.co/m-a-p/SheetSage2) - Official audio-to-score transcription: melody, chords, beats, key and structure as editable lead sheets for covers.
- [MERT-v2-FullSong](https://huggingface.co/m-a-p/MERT-v2-FullSong) - Official full-song music representations and the encoder of SheetSage2.
- [MuScriptor](https://github.com/muscriptor/muscriptor) - Multi-instrument audio-to-MIDI transcription by Kyutai and Mirelo, useful for turning takes and stems into MIDI (code MIT, weights CC BY-NC 4.0).
- [muscriptor.cpp](https://github.com/DamRsn/muscriptor.cpp) - GGUF conversion and a local C++ runtime for MuScriptor.
- [SheetSage2-GGUF](https://huggingface.co/audio-cpp/SheetSage2-GGUF) - SheetSage2 converted for audio.cpp.
- [SheetSage2-Refined](https://github.com/anime-song/SheetSage2-Refined) - Fine-tune of SheetSage2 that is stronger on bars, time signatures, detailed chords and keys.

## Datasets and Benchmarks

- [WildSongBench](https://huggingface.co/datasets/m-a-p/WildSongBench) - The official 192 prompts and evaluation protocol behind the YuE2 benchmark scores.
- [yue2-minted-corpus](https://huggingface.co/datasets/Mothersuperior/yue2-minted-corpus) - Songs generated by YuE2-3B with every intermediate kept, for training audio-to-token encoders.

## Online Demos

- [YuE2 Online by NOIZ](https://yue.noizai.net/) - Free in-browser YuE2, linked from the official README.
- [Hum to Song](https://huggingface.co/spaces/Mothersuperior/yue2-hum-to-song) - Hugging Face Space that turns a hummed melody into a finished song.
- [YuE2 Create](https://huggingface.co/spaces/directedbykobyperez/YuE2-Create) - Hugging Face Space for song creation with YuE2.
- [YuE2 Particle Sliders](https://huggingface.co/spaces/ntc-ai/yue2-particle-sliders) - Hugging Face Space with off and on comparisons for 16 voice and genre sliders.
- [YuE2-3B Music Generator](https://huggingface.co/spaces/mrfakename/yue2-3b) - Hugging Face Space for songs and covers from style prompts and lyrics.

## Guides

- [Covers](https://github.com/multimodal-art-projection/YuE/blob/main/docs/covers.md) - Official guide to transcribing a recording with SheetSage2 and generating a cover from its score.
- [Generation](https://github.com/multimodal-art-projection/YuE/blob/main/docs/generation.md) - Official guide to the generation options.
- [Hardware](https://github.com/multimodal-art-projection/YuE/blob/main/docs/hardware.md) - Official notes on memory and hardware requirements.
- [Score Editing](https://github.com/multimodal-art-projection/YuE/blob/main/docs/editing.md) - Official guide to editing a song through its score.
- [Ruach Studio Guide](https://github.com/igrbible/Ruach_Studio/blob/main/docs/GUIDE.md) - User guide of Ruach Studio, from prompts and scores to adapters and the refiner. Written by this list's maintainers.

## Contributing

Contributions are welcome. Read the [contribution guidelines](contributing.md) first: every entry needs a working link, a one-line description and a real connection to YuE2.

---

Maintained by the authors of [Ruach Studio](https://ruachstudio.art) ([igrbible on GitHub](https://github.com/igrbible), [goldhub on Hugging Face](https://huggingface.co/goldhub)). Our own projects are marked as such and follow the same rules as everyone else's.
