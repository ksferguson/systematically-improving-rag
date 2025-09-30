# Week 2: Fine-tuning Embedding Models for Retrieval

## Overview

This week focuses on one of the most impactful ways to improve RAG system performance: fine-tuning embedding models for your specific domain. Generic embedding models are trained on broad internet data and may not capture the nuances of your particular use case. By fine-tuning these models with domain-specific data, you can achieve significant improvements in retrieval quality.

**Note**: As of September 2025, Cohere no longer supports fine-tuning. This week now focuses primarily on open-source fine-tuning using sentence-transformers, which gives you complete control over the training process and demonstrates 15-30% improvements in key retrieval metrics, making fine-tuning one of the highest-ROI optimizations for RAG systems.

## Learning Objectives

By the end of this week, you'll be able to:

- Generate high-quality synthetic training data for embedding fine-tuning
- Implement manual review processes to ensure training data quality
- Fine-tune embedding models using open-source tools like sentence-transformers
- Create effective training datasets with hard and semi-hard negatives
- Evaluate fine-tuned models against baselines using established metrics
- Deploy fine-tuned models to Hugging Face Hub for production use
- Understand triplet loss and semi-hard negative mining techniques

## Notebooks

### 1. Synthetic-Transactions.ipynb

**Purpose**: Generate and validate high-quality synthetic transaction data for embedding model fine-tuning

**What You'll Learn**:

- Structured data generation using Pydantic models and instructor
- Quality control through manual review processes
- Dataset preparation techniques for embedding training
- Evaluation setup with proper train/eval splits

**What You'll Build**:

- Synthetic transaction dataset with realistic descriptions
- Manual review interface using Streamlit
- Evaluation pipeline with LanceDB for measuring improvements

### 2. Open Source Models.ipynb (Recommended)

**Purpose**: Fine-tune open-source embedding models with complete control over the training process

**What You'll Learn**:

- Triplet loss training with semi-hard negative mining
- SentenceTransformerTrainer configuration and usage
- Model deployment to Hugging Face Hub
- Hyperparameter tuning and evaluation techniques

**What You'll Build**:

- Fine-tuned BAAI/bge-base-en embedding model
- Training pipeline using sentence-transformers
- Deployable model on Hugging Face Hub

### 3. Finetune Cohere.ipynb (Deprecated - Reference Only)

> **Note**: As of September 2025, Cohere no longer supports fine-tuning. Please focus on the Open Source Models notebook instead. This notebook is kept for reference purposes only.

**Purpose**: Fine-tune a Cohere re-ranker model using managed services for simplified deployment

**What You'll Learn**:

- Hard negative mining techniques for effective training
- Working with Cohere's fine-tuning API (deprecated)
- Comparative evaluation of base vs. fine-tuned models
- Performance analysis and visualization techniques

**What You'll Build**:

- Fine-tuned Cohere re-ranker model (no longer supported)
- Training dataset with carefully selected hard negatives
- Performance comparison visualizations

## Key Concepts

- **Hard Negatives**: Training examples that are similar but incorrect, forcing the model to learn fine distinctions
- **Semi-Hard Negatives**: Moderately challenging negative examples that provide optimal learning signals
- **Triplet Loss**: Training objective that brings positive examples closer while pushing negatives away
- **Domain Adaptation**: Specializing general models for specific use cases through fine-tuning
- **Re-ranker Models**: Second-stage models that reorder initial retrieval results for better precision

## Prerequisites

### Knowledge Requirements

- Understanding of embedding models and vector similarity
- Basic knowledge of model training concepts (loss functions, epochs, batch size)
- Familiarity with the evaluation metrics from Week 1

### Technical Requirements

- Python packages: `sentence-transformers`, `lancedb`, `braintrust`, `pydantic`, `openai`, `streamlit`
- API keys: OpenAI API access, Hugging Face token with write access
- Hardware: GPU recommended for fine-tuning (CPU possible but slower)

## Project Structure

```text
week2/
├── README.md
├── Synthetic-Transactions.ipynb
├── Finetune Cohere.ipynb
├── Open Source Models.ipynb
├── data/
│   ├── categories.json
│   ├── cleaned.jsonl
│   └── training_data/
├── assets/
│   ├── hard_negatives.png
│   └── semi-hard-negative.png
├── helpers.py
└── label.py
```

## Datasets

- **Transaction Categories**: 24 financial transaction types with sample descriptions for generating training data
- **Cleaned Transactions**: Manually reviewed and approved transaction examples ensuring high-quality training signals
- **Training Pairs**: Query-document pairs with hard negatives for effective model fine-tuning

## Expected Outcomes

After completing this week's materials, you'll have:

1. A high-quality domain-specific training dataset with validated examples
2. Fine-tuned embedding models showing 15-30% improvement in retrieval metrics
3. Hands-on experience with open-source fine-tuning using sentence-transformers
4. Deployed models on Hugging Face Hub ready for production use
5. Understanding of triplet loss, semi-hard negatives, and hyperparameter tuning

## Common Issues and Solutions

### Issue 1: Low quality synthetic data affecting model performance

**Solution**: Use the manual review process (label.py) to filter out poor examples. Quality matters more than quantity for fine-tuning.

### Issue 2: Overfitting on small datasets

**Solution**: Ensure sufficient dataset diversity and use proper validation splits. Monitor validation metrics during training.

### Issue 3: GPU memory errors during open-source training

**Solution**: Reduce batch size or use gradient accumulation. Consider using smaller base models if memory is limited.

## Next Steps

- Complete notebooks in order to build upon concepts progressively
- Experiment with different base models and hyperparameter configurations
- Review Week 3 content to prepare for advanced retrieval techniques
- Explore different negative sampling strategies (hard vs. semi-hard negatives)

## Additional Resources

- [Sentence-BERT: Sentence Embeddings using Siamese BERT-Networks](https://arxiv.org/abs/1908.10084)
- [Cohere Rerank Documentation](https://docs.cohere.com/docs/reranking)
- [Hugging Face Model Hub](https://huggingface.co/models)
- [Efficient Natural Language Response Suggestion for Smart Reply](https://arxiv.org/abs/1705.00652)

---

## **Note**: Ensure you've completed Week 1's evaluation framework before starting these notebooks. The metrics and benchmarking tools from Week 1 are essential for measuring the improvements achieved through fine-tuning.

--8<--
"snippets/enrollment-button.md"
--8<--

---
