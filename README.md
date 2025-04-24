# ExtractiveSummarization-BERT-Static-GPT

This repository contains the source code and evaluation framework for a comparative study on extractive summarization using three representative NLP methods across different technological generations:

- Static Embedding (non-contextual representation)  
- BERTSum (pre-trained Transformer-based model)  
- GPT-4o (large-scale generative language model with prompt-based summarization)

## Project Overview

This project is developed as part of an academic coursework assignment in natural language processing (NLP). It aims to explore how different language modeling paradigms affect the performance of extractive summarization.

Dataset: CNN / DailyMail  
Evaluation Metric: ROUGE-1, ROUGE-2, ROUGE-L

## Methodology

1. **BERTSum (Pre-trained Language Model)**  
   - This implementation is based on [nlpyang/BertSum](https://github.com/nlpyang/BertSum).  
   - Uses a fine-tuned BERT encoder to obtain contextual sentence embeddings.  
   - Applies a Transformer-based inter-sentence encoder to score sentence importance.  
   - Selects top-scoring sentences for the extractive summary.  

2. **Static Embedding (Non-contextual Embedding)**  
   - Freezes pre-trained BERT word embeddings as static vectors.  
   - Replaces sentence CLS token with average pooling.  
   - Lacks contextual awareness and serves as a baseline for comparison.  

3. **GPT-4o (Large Language Model)**  
   - Employs the GPT-4o API to generate extractive summaries.  
   - Uses prompt engineering to guide the LLM in selecting key sentences verbatim.  
   - No model fine-tuning is required, demonstrating strong zero-shot capability.  

## Results

| Method                    | ROUGE-1 | ROUGE-2 | ROUGE-L |
|--------------------------|---------|---------|---------|
| GPT-4o (LLM)             | 45.38   | 29.26   | 41.65   |
| BERTSum (Pre-trained LM) | 41.12   | 18.40   | 37.56   |
| Static Embedding (NLM)   | 24.31   | 5.79    | 21.93   |

## Analysis & Findings

- GPT-4o achieved the best performance across all ROUGE metrics, demonstrating superior phrase-level understanding and coherence in sentence selection.
- BERTSum maintained strong performance in single-word and sentence-level structures, due to its Transformer-based encoding and task-specific tuning.
- Static Embedding performed significantly lower, highlighting the importance of contextual representation in modern summarization tasks.

## Conclusion

This study provides empirical support for the evolution of summarization models from static representations to contextualized pre-training, and finally to large-scale LLMs capable of prompt-driven summarization. The results demonstrate that both model architecture and training methodology are key factors influencing summarization quality.

## Repository Structure

ExtractiveSummarization-BERT-Static-GPT/  
├── bertsum/                   # BERTSum implementation (based on nlpyang/BertSum)  
├── static/                    # Static embedding modification and mean pooling  
├── LLM-for-summary/           # GPT-4o prompt-based extractive summarization API interface  
├── pyrouge/                   # ROUGE evaluation tool configuration  
└── README.md                  # Project documentation  

## Contact

Author: Hung-Yun Lin (林宏昀)  
Email: 41147004S@ntnu.edu.tw  
Course: CS115 – Natural Language Processing  
Institution: National Taiwan Normal University
