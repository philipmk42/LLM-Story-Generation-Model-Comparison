# LLM Story Generation Model Comparison

An interactive comparison of different transformer architectures for story generation using GPT-2, DistilGPT-2, and FLAN-T5.

## Overview

This project builds a Streamlit application to compare the story generation capabilities of three transformer-based language models:

- **GPT-2** — Decoder-only autoregressive model
- **DistilGPT-2** — Distilled, smaller version of GPT-2
- **FLAN-T5** — Instruction-tuned encoder-decoder model

Users can input prompts, adjust generation parameters, and evaluate outputs using both automatic metrics and human judgment.

## Features

- Interactive prompt input with sample prompts
- Adjustable generation parameters (max length, temperature, top-p)
- Side-by-side story generation from multiple models
- Automatic evaluation using **BLEU** and **ROUGE-L**
- Human evaluation sliders (Fluency, Coherence, Creativity)
- Comparative bar charts and metric tables

## Tech Stack

- **Python**
- **Hugging Face Transformers**
- **PyTorch**
- **Streamlit**
- **Evaluate** library (BLEU & ROUGE)
- **NLTK, Pandas, Matplotlib**

## How It Works

1. User provides a story prompt.
2. The prompt is formatted differently based on model type (causal vs seq2seq).
3. Each model generates a continuation/story.
4. Generated text is evaluated against a reference using BLEU and ROUGE-L.
5. Users rate the outputs on fluency, coherence, and creativity.
6. Results are visualized for easy model comparison.

## Key Learnings

- Different transformer architectures (decoder-only vs encoder-decoder) behave differently in open-ended generation tasks.
- Decoding parameters (temperature, top-p) significantly affect output quality and diversity.
- Automatic metrics like BLEU and ROUGE have limitations when evaluating creative text generation.
- Human evaluation remains essential for assessing qualities like creativity and coherence.

## Limitations

- Uses a static placeholder reference for automatic metrics.
- Human evaluation is collected via sliders but not persisted across sessions.
- No fine-tuning was performed — only inference and comparison.

## Installation & Usage

```bash
git clone https://github.com/philipmk42/LLM-Story-Generation-Model-Comparison.git
cd LLM-Story-Generation-Model-Comparison
pip install -r requirements.txt
streamlit run app.py
