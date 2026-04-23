# Presentation Recording

## RAG-Powered Biomedical Q&A with Semantic Hallucination Detection

**Course:** AI In Healthcare | University of Texas at Austin | Spring 2026
**Author:** Sritama Paul

---

## Watch the Presentation

Click the link below to view the recorded presentation:

**[▶ Watch Presentation Recording](https://1drv.ms/f/c/53004514932505b3/IgCMszJ0-YhiRo6jgC1sINIAAWYm3Xw-i6C0EaHkAomQX_g?e=cFbTzK)**

> The video is hosted on Microsoft OneDrive. Click the link and press the play button to stream it directly in your browser, or use the download button to save a local copy.

---

## Presentation Overview

The recording covers the following sections:

| Section | Topic |
|---|---|
| Introduction | LLM hallucination in clinical AI and why it matters |
| Dataset & Methods | PubMedQA, dual embedding models, 6 experimental conditions, and the hallucination scoring pipeline |
| Results | Accuracy, hallucination rate, ROUGE-L, LLM-as-Judge scores, and the key scorer disagreement finding |
| Future Directions | Improvements and extensions for future work |

---

## Key Findings Covered in the Video

- **3.2×** reduction in hallucination rate when using RAG versus No-RAG (OpenAI RAG Zero-shot vs No-RAG Zero-shot)
- **68%** best answer accuracy achieved by OpenAI RAG CoT
- **+48 percentage point** scorer gap — PubMedBERT rates No-RAG CoT answers as 86% hallucinated versus OpenAI's 38% — revealing that general-purpose embedders systematically underestimate clinical hallucination in free reasoning chains

---

## Related Files

- [`final_project/`](./final_project/) — Code, notebook, and report
- [`final_project/presentation/`](./final_project/presentation/) — Slide deck (`.pptx`)
