# 🎬 ComfyUI Image-to-Video Filters

![ComfyUI](https://img.shields.io/badge/ComfyUI-Workflow-blue?style=for-the-badge)
![Wan2.1](https://img.shields.io/badge/Model-Wan2.1%2F2.2-green?style=for-the-badge&logo=openai)
![Status](https://img.shields.io/badge/Status-Active-success?style=for-the-badge)

A professional, high-quality **Image-to-Video (I2V)** generation workflow for [ComfyUI](https://github.com/comfyanonymous/ComfyUI). This repository contains optimized JSON workflows and curated prompts designed to create cinematic, realistic, and creative video filters from static images using the Wan 2.1/2.2 diffusion models.

## ✨ Features

- **🚀 Optimized Workflow:** Pre-configured `img2vid.json` workflow for Wan2.1/2.2 models.
- **🎨 Cinematic Filters:** Includes a comprehensive library of prompting presets for various styles (Cinematic, Product Showcase, Surreal, Nature, etc.).
- **🔧 Easy Customization:** Modular workflow design allows for easy tweaking of parameters like motion strength, seed, and resolution.
- **📷 High Fidelity:** Tuned for high-quality output using GGUF quantization for efficient memory usage without sacrificing too much detail.

## 📂 Repository Structure

```
├── workflows/          # ComfyUI JSON workflows
│   └── img2vid.json    # Main Image-to-Video workflow
├── prompts/            # Curated text prompts for different effects
│   └── Image2Vid_Prompting_filters.txt
├── assets/             # Example images and assets (optional)
├── .gitignore          # Git ignore file for models and outputs
└── README.md           # This documentation
```

## 🛠️ Prerequisites

To use this workflow, you need **ComfyUI** installed along with the following custom nodes and models:

### Required Custom Nodes
Ensure you have the following installed via **ComfyUI Manager**:
1.  **ComfyUI-GGUF**: For loading GGUF quantized models (`UnetLoaderGGUF`).
2.  **ComfyUI-VideoHelperSuite**: For saving and combining video frames (`VHS_VideoCombine`).
3.  **ComfyUI-Wan**: (Or equivalent native support) for `WanImageToVideo` nodes.

### Required Models
Download these models and place them in your `ComfyUI/models/` directory:
- **UNET**: `Wan2.2-I2V-A14B-LowNoise-Q8_0.gguf` (or HighNoise variant) -> `models/unet/`
- **VAE**: `wan_2.1_vae.safetensors` -> `models/vae/`
- **CLIP**: `umt5_xxl_fp8_e4m3fn_scaled.safetensors` -> `models/clip/`
- **CLIP Vision**: `clip_vision_h.safetensors` -> `models/clip_vision/`

## 🚀 Usage Guide

1.  **Load the Workflow**:
    - Open ComfyUI.
    - Drag and drop `workflows/img2vid.json` into the window or use the "Load" button.

2.  **Select Your Image**:
    - Locate the **Load Image** node.
    - Upload the source image you want to animate.

3.  **Choose a Prompt**:
    - Open `prompts/Image2Vid_Prompting_filters.txt`.
    - Select a prompt style (e.g., *"Cinematic street serum shot"* or *"Flying"*).
    - Copy the desired prompt text into the **positive prompt** text box (green generic node or `CLIPTextEncode`).
    - *Optional*: Adjust the **negative prompt** if needed.

4.  **Generate**:
    - Click **Queue Prompt**.
    - The output video will be saved in your ComfyUI output folder.

## 📝 Prompting Filters

This project includes a collection of specialized prompts located in `prompts/Image2Vid_Prompting_filters.txt`. Some examples include:

- **Commercial Product**: "Cinematic street serum shot", "Under the clouds"
- **Nature & Scenery**: "Video ship scene", "Natural ocean waves"
- **Creative/Surreal**: "Zombie Transformation", "Slimy look"
- **Motion Effects**: "Flying", "Zoom into the eye"

## 🤝 Contributing

Contributions are welcome! If you have optimized versions of the workflow or new creative prompts, please feel free to submit a Pull Request.

1.  Fork the repository.
2.  Create a feature branch (`git checkout -b feature/NewFilter`).
3.  Commit your changes.
4.  Push to the branch.
5.  Open a Pull Request.

## 📄 License

This project is open-source and available for personal and commercial use under the MIT License.
