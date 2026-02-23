# AI-Comic-Book-SDXL
An AI-generated comic book built with Stable Diffusion XL, Python, and perfectly locked character consistency.
# 🦸‍♂️ Zain and the Power of Kindness: AI Comic Book

An end-to-end Python pipeline for generating a highly consistent, 14-panel comic book using **Stable Diffusion XL 1.0 (SDXL)**. 

This project solves the common AI issue of "character morphing" by engineering highly optimized, comma-separated token prompts and locking seeds to maintain strict visual consistency for the characters and environments.

## 🛠️ Technical Stack & Implementation
* **Model:** Stable Diffusion XL 1.0 (`stabilityai/stable-diffusion-xl-base-1.0`)
* **Hardware Limit Solved:** Optimized for Google Colab T4 GPU (16GB VRAM) using `fp16` precision and `enable_attention_slicing()`.
* **Scheduler:** DPM++ 2M Karras (High-quality generation in just 30 steps).
* **Token Guard:** Integrated OpenAI's `CLIPTokenizer` to mathematically ensure all prompts stay under the strict 77-token limit, preventing prompt truncation.
* **Text Processing:** Custom Python `PIL.ImageDraw` pipeline to dynamically generate and "burn" stylized narration boxes (yellow) and speech bubbles (white) directly onto the generated 1024x1024 images without AI text garbling.
* **Evaluation:** Scored via CLIP metrics, with image-text alignment consistently scoring above 30 (Masterpiece tier).

## 📂 Repository Contents
* `zain_comic_book.ipynb`: The complete Google Colab codebase (Model loading, token validation, image generation, and PDF compilation).
* `Zain_Comic_Book.pdf`: The final, compiled 14-page comic book.
* `clip_scores.csv`: The mathematical evaluation of prompt-to-image alignment.

## 🚀 How to Run
1. Open the `.ipynb` file in Google Colab.
2. Ensure you are using a **T4 GPU** runtime.
3. Run all cells. The script will automatically download the SDXL weights, generate the panels, burn the text, and compile the final PDF.
