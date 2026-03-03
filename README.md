<div align="center">

<img src="src-tauri/icons/Square310x310Logo.png" alt="Dictara" width="128" height="128">

# Dictara

**Typing is slow. Speaking isn't.**

Free · Bring Your Own Key · Speech-to-Text

Turn your spoken words into text — in any app, any language.

[![Download](https://img.shields.io/badge/Download-Dictara-blue?style=for-the-badge)](https://dictara.app/)

[**Get Dictara**](https://dictara.app/)

</div>

---

## How It Works

1. **Install** — Download and install Dictara
2. **Configure** — Add your OpenAI or Azure OpenAI API key
3. **Dictate** — Hold `FN` to record, release to transcribe. Or press `FN+Space` for hands-free mode
4. **Done** — Text is automatically pasted wherever your cursor is — in any app

---

## Troubleshooting

### Emoji Picker Appears When Using Fn Key

If the emoji picker (or character viewer) appears when you press the Fn/Globe (🌐) key, you need to change your macOS keyboard settings:

**Via System Settings (Recommended):**
1. Open **System Settings** → **Keyboard**
2. Find **"Press 🌐 key to"** dropdown
3. Change it to **"Do Nothing"** or **"Change Input Source"**

**Via Terminal:**
```bash
# Set Globe key to "Do Nothing"
defaults write com.apple.HIToolbox AppleFnUsageType -int 0

# Then log out and log back in, or restart your Mac
```

> **Note:** This is a macOS limitation. The Fn/Globe key triggers the emoji picker at a system level that applications cannot intercept.

---

## Local Transcription Models

Dictara supports offline speech-to-text using locally downloaded models. No internet connection required after download.

### Available Models

#### Parakeet Models (NVIDIA)
**Source:** [huggingface.co/istupakov/parakeet-tdt-0.6b-v3-onnx](https://huggingface.co/istupakov/parakeet-tdt-0.6b-v3-onnx)

| Model | Size | Files | Download URLs |
|-------|------|-------|---------------|
| **Parakeet V3 INT8** | ~639 MB | encoder-model.int8.onnx | [encoder-model.int8.onnx](https://huggingface.co/istupakov/parakeet-tdt-0.6b-v3-onnx/resolve/main/encoder-model.int8.onnx) |
| | | decoder_joint-model.int8.onnx | [decoder_joint-model.int8.onnx](https://huggingface.co/istupakov/parakeet-tdt-0.6b-v3-onnx/resolve/main/decoder_joint-model.int8.onnx) |
| | | vocab.txt | [vocab.txt](https://huggingface.co/istupakov/parakeet-tdt-0.6b-v3-onnx/resolve/main/vocab.txt) |
| **Parakeet V3 FP32** | ~2.37 GB | encoder-model.onnx | [encoder-model.onnx](https://huggingface.co/istupakov/parakeet-tdt-0.6b-v3-onnx/resolve/main/encoder-model.onnx) |
| | | encoder-model.onnx.data | [encoder-model.onnx.data](https://huggingface.co/istupakov/parakeet-tdt-0.6b-v3-onnx/resolve/main/encoder-model.onnx.data) |
| | | decoder_joint-model.onnx | [decoder_joint-model.onnx](https://huggingface.co/istupakov/parakeet-tdt-0.6b-v3-onnx/resolve/main/decoder_joint-model.onnx) |
| | | vocab.txt | [vocab.txt](https://huggingface.co/istupakov/parakeet-tdt-0.6b-v3-onnx/resolve/main/vocab.txt) |

**Parakeet features:**
- Supports 25 languages
- Optimized for CPU inference
- INT8 variant recommended for 8GB RAM
- FP32 variant for best quality (16GB+ RAM recommended)

#### Whisper Models (ggerganov/whisper.cpp)
**Source:** [huggingface.co/ggerganov/whisper.cpp](https://huggingface.co/ggerganov/whisper.cpp)

| Model | Size | Download URL |
|-------|------|--------------|
| **Whisper Small** | ~465 MB | [ggml-small.bin](https://huggingface.co/ggerganov/whisper.cpp/resolve/main/ggml-small.bin) |
| **Whisper Medium** | ~1.43 GB | [ggml-medium.bin](https://huggingface.co/ggerganov/whisper.cpp/resolve/main/ggml-medium.bin) |
| **Whisper Large v3 Turbo** | ~1.51 GB | [ggml-large-v3-turbo.bin](https://huggingface.co/ggerganov/whisper.cpp/resolve/main/ggml-large-v3-turbo.bin) |
| **Whisper Large v3** | ~2.88 GB | [ggml-large-v3.bin](https://huggingface.co/ggerganov/whisper.cpp/resolve/main/ggml-large-v3.bin) |

**Whisper features:**
- English-focused (some multilingual support)
- ggml format for efficient CPU/GPU inference
- Small variant recommended for 8GB RAM
- Medium/Large variants for 16GB+ RAM

### Model Storage

Models are stored in:
```
~/Library/Application Support/app.dictara/models/
```

All downloads include SHA-256 checksum verification to ensure integrity.

---

## Contributing

We welcome contributions! Please see our [Contributing Guide](.github/CONTRIBUTING.md) to get started.

## License

This project is licensed under the MIT License — see the [LICENSE](LICENSE) file for details.
