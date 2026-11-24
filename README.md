# Making Conversational Context Visible: A Context-Aware Emotion Interpretation Interface

## Project Overview

This project investigates how conversational context affects emotion recognition in audio language models and how these effects can be presented through a human-computer interaction (HCI) interface.

We evaluate **Qwen2-Audio-7B-Instruct** on the **MELD (Multimodal EmotionLines Dataset)** using four input conditions:

1. **Audio-only:** The target utterance is provided as audio.
2. **Audio with context:** The target utterance and its two preceding utterances are provided as audio.
3. **Text-only:** The transcript of the target utterance is provided as text.
4. **Text with context:** The target transcript and two preceding utterance transcripts are provided as text.

The study examines whether adding conversational context improves emotion predictions or changes their accuracy. Based on the experimental findings, we designed a Figma interface that allows users to inspect the target utterance, surrounding dialogue, model predictions, reference emotion labels, and prediction changes.

## Research Domain

- **Domain:** Human-Computer Interaction (HCI) and Computer Science (CS)
- **Selected Topic:** AI-Driven Interaction & Intelligent Interfaces
- **Research Area:** Emotion Recognition, Audio Language Models, Conversational Context, and Human-AI Interaction

## Research Objectives

- Evaluate the effect of conversational context on emotion recognition.
- Compare audio-based and text-based predictions under four input conditions.
- Examine how frequently predictions change when context is introduced.
- Identify whether prediction changes correct or worsen the model's output.
- Design an interface that makes model predictions, context effects, and limitations easier to inspect.

## Dataset

The experiment uses the **MELD dataset**, which contains multi-party conversations from the television series *Friends*.

The dataset provides utterances labelled with seven emotion categories:

- Anger
- Disgust
- Fear
- Joy
- Neutral
- Sadness
- Surprise

The final paired evaluation uses **1,918 utterances from the MELD test split**.

## Model and Implementation

- **Model:** Qwen/Qwen2-Audio-7B-Instruct
- **Platform:** Google Colab
- **GPU:** NVIDIA Tesla T4
- **Quantization:** 4-bit
- **Evaluation:** Four input conditions using the same paired utterances
- **Programming:** Python

## Experimental Results

The following table presents the overall evaluation results.

| Input Condition | Accuracy | Macro-Precision | Macro-Recall | Macro-F1 |
|---|---:|---:|---:|---:|
| Audio-only | 45.67% | 42.41% | 34.16% | 31.94% |
| Audio with context | 25.81% | 39.74% | 29.20% | 21.42% |
| Text-only | 54.22% | 44.01% | 43.56% | 40.72% |
| Text with context | 42.49% | 39.15% | 45.78% | 35.97% |

### Key Findings

- Adding context reduced audio accuracy by **19.86 percentage points**.
- Adding context reduced text accuracy by **11.73 percentage points**.
- Macro-F1 decreased for both audio and text conditions.
- Predictions changed for **54.28% of audio inputs** and **42.23% of text inputs**.
- For audio, context-induced changes more frequently turned correct predictions into incorrect ones than incorrect predictions into correct ones.

These findings indicate that adding conversational context does not necessarily improve emotion recognition.

## HCI Interface Prototype

A Figma prototype was designed to make the model's behaviour more transparent and interpretable.

The interface presents:

- The target utterance.
- The two preceding conversational utterances.
- Predictions from all four input conditions.
- The MELD reference emotion label.
- Indicators showing whether predictions changed after adding context.
- Warnings and limitations to distinguish model predictions from reference annotations.

The prototype is intended to help users inspect and compare model outputs rather than presenting a single emotion prediction as a definitive interpretation.

**Note:** The interface is a Figma prototype based on precomputed experimental results. It is not a live emotion recognition application.

## Evaluation

The research includes two types of evaluation:

1. **Model Evaluation:** Accuracy, macro-precision, macro-recall, macro-F1, and prediction-change analysis across the four input conditions.
2. **Interface Technical Evaluation:** Inspection of data correctness, prediction consistency, context representation, comparison accuracy, information clarity, and limitation transparency.

No human-participant usability study was conducted in this project.

## Repository Structure

Key project files include:

| File | Description |
|---|---|
| `qwen_meld_full_results.csv` | Model predictions across the four input conditions |
| `cleaned_complete_predictions.csv` | Cleaned prediction records used for evaluation |
| `overall_metrics.csv` | Overall evaluation metrics |
| `per_emotion_metrics.csv` | Evaluation metrics for individual emotion categories |
| `meld_dataset.ipynb` | Google Colab notebook containing the experimental workflow |
| Figma assets | Interface prototype screens and design materials |

## Limitations

- The experiment evaluates only one audio language model.
- Evaluation is limited to English-language conversations from MELD.
- Only two preceding utterances are used as conversational context.
- The dataset consists of scripted television dialogue and may not represent natural everyday conversations.
- The model was evaluated using 4-bit quantization on a Tesla T4 GPU.
- No human-participant usability study was conducted.

## Future Work

Future research can explore:

- Evaluating additional audio language models.
- Testing multilingual conversational datasets.
- Comparing different context lengths.
- Investigating the effects of speaker identity and dialogue structure.
- Conducting human-participant studies to evaluate usability, transparency, and user understanding.
- Developing a fully interactive application for exploring conversational emotion predictions.

## Authors

**Khansa Khalid** and project team  
BS Computer Science  
FAST National University of Computer and Emerging Sciences

## Repository

[GitHub Repository](https://github.com/khansakhalid165-hub/AHCI_RESEARCH-REPORT)

## Keywords

Emotion Recognition in Conversation, Audio Language Models, Qwen2-Audio, Conversational Context, MELD Dataset, Human-Computer Interaction, Explainable Interfaces, Human-AI Interaction.
