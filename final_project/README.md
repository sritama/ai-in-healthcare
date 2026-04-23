# AI in Healthcare: RAG Hallucination Analysis with Two Models

## Project Purpose

This project explores the phenomenon of hallucination in Retrieval-Augmented Generation (RAG) systems within the context of healthcare applications. Hallucination refers to the generation of incorrect or fabricated information by AI models, which can be particularly problematic in medical domains where accuracy is critical.

The study compares two different embedding models:
- **OpenAI Embeddings**: A proprietary model known for high performance in general-purpose tasks
- **PubMedBERT**: A domain-specific model trained on biomedical literature, potentially better suited for healthcare-related queries

### Key Objectives
- Evaluate the frequency and types of hallucinations produced by each model in RAG setups
- Analyze how domain-specific training (PubMedBERT) vs. general-purpose training (OpenAI) affects hallucination rates
- Provide insights into model selection for healthcare AI applications
- Contribute to the understanding of AI reliability in medical information retrieval and generation

### Methodology
The analysis involves:
- Generating embeddings for medical contexts using both models
- Implementing RAG pipelines with different retrieval strategies
- Scoring and comparing hallucination instances across various healthcare-related queries
- Statistical analysis of results to identify patterns and differences

### Data and Results
Results are stored in the `csv_files/` directory, including:
- Embedding comparisons
- Judge scores and summaries
- RAG performance metrics across different conditions

This work aims to inform the development of more reliable AI systems for healthcare, emphasizing the importance of model evaluation in domain-specific applications.