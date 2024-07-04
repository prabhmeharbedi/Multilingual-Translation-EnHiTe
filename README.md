# Multilingual Translation Project

## Project Overview
The Multilingual Translation project focuses on training a Transformer model from scratch to translate English to Hindi and Telugu. The model employs a sequence-to-sequence architecture with an encoder-decoder setup. It uses specific tokens to identify the target language and processes translations accordingly.

## Description of NLP Application and Dataset
The project utilizes the OPUS-100 dataset, an English-centric multilingual corpus covering 100 languages. OPUS-100 includes a large collection of parallel sentences in multiple languages, designed for multilingual machine translation tasks. For this project, we focus on the English-Hindi (en-hi) and English-Telugu (en-te) subsets.

## Description of Transformer Model Used
- **Token Identification**: The model understands which language to translate to based on the preceding beginning-of-sentence token:
  - English sentences start with `<s-en>` token
  - Hindi sentences start with `<s-hi>` token
  - Telugu sentences start with `<s-te>` token
  - All sentences end with `</s>` token
- **Model Architecture**:
  - Trained as a Sequence-to-Sequence transformer model with an encoder-decoder style architecture. The encoder handles English, and the decoder handles both Hindi and Telugu.
  - Implemented a 7M parameter model.
  - The model consists of embedding layers that combine class and positional embeddings, followed by multiple stacked encoder and decoder blocks. Each encoder block includes attention and feedforward layers, while each decoder block additionally includes cross-attention layers to process the encoder's output.
  - The forward pass processes source and target sequences through these blocks, resulting in logits for next-token prediction.
  - The model features a generate method for autoregressive sequence generation, either deterministically or probabilistically.
  - Overall, the Seq2SeqTransformer is highly effective for transforming input sequences into output sequences, leveraging the strengths of the Transformer architecture.
