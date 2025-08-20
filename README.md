# ReProCon: Scalable and Resource-Efficient Few-Shot Biomedical NER

This repository contains the implementation of **ReProCon**, a novel few-shot Named Entity Recognition (NER) framework for biomedical text, as described in our arXiv preprint:

**ReProCon: Scalable and Resource-Efficient Few-Shot Biomedical Named Entity Recognition**  
Jeongkyun Yoo, Nela Riddle, Andrew Hoblitzell  
arXiv: [insert arXiv ID, e.g., arXiv:2508.XXXXX]  
[Link to paper]

ReProCon combines multi-prototype modeling, cosine-contrastive learning, and Reptile meta-learning to achieve scalable and resource-efficient NER. It exhibits only a 7.8% Macro-F1 drop when scaling from 19 to 50 categories and achieves 99% of BERT performance using a lightweight fastText + BiLSTM encoder, making it ideal for resource-constrained biomedical applications.

## Language Model Download
To reproduce the experiments, download the following language models to the specified directories in your Colab environment:

1. **fastText**:
   - Download pre-trained fastText embeddings (`cc.en.300.bin`) from [fastText website](https://fasttext.cc/docs/en/crawl-vectors.html).
   - Place in: `./language_model/fasttext/fasttext/cc.en.300.bin`

2. **BERT**:
   - Download `bert-base-cased` from Hugging Face Transformers.
   - Place in: `./language_model/bert/tokenizer` for tokenizer, and `./language_model/bert/tokenizer/transformer` for transformer

**Note**: Ensure these models are downloaded to the specified directories before running the code, as the scripts expect these paths.

## Reproducing Results
- **Macro-F1**: The fastText + BiLSTM model achieves ~47.95 (19-way) and ~49.45 (50-way), comparable to BERT (99% of BERT performance).
- **Scalability**: Only 7.8% F1 drop when scaling from 19 to 50 categories (Table 2 in paper).
- **Ablation**: Multi-prototype and contrastive learning critical for class imbalance.

## License
This code is licensed under the MIT License. The dataset (MedMentions) is subject to UMLS licensing terms. The paper is licensed under CC BY 4.0.

## Contact
For questions, contact the corresponding author:  
Andrew Hoblitzell (ahoblitz@purdue.edu)
