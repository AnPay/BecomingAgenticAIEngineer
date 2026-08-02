# Embeddings

Imagine asking an AI:

> "What's the capital of India?"

To us, it's just a simple sentence. But to a neural network, it's nothing more than a sequence of symbols.

Before an LLM can understand or reason about language, those symbols must be transformed into something it can process. That's where **embeddings** come in.

Embeddings convert language into meaningful numerical representations, enabling models to understand relationships between words rather than treating them as isolated pieces of text.

## What are Embeddings?

Embeddings are **dense numerical vector representations of tokens** that capture their semantic meaning.

Machine learning models cannot understand text directly—they operate on numbers. Instead of representing text as simple token IDs, embeddings map each token to a high-dimensional vector where semantically similar tokens are positioned closer together.

For example, the embeddings for **"car"** and **"automobile"** are much closer than the embeddings for **"car"** and **"banana"**.

---

## Why Do We Need Embeddings?

Embeddings enable neural networks to understand semantic relationships between words.

They are essential because:

- Neural networks process numbers, not text.
- They capture semantic similarity between tokens.
- They provide meaningful numerical representations for transformer models.
- They enable similarity search in applications like RAG and recommendation systems.

Without embeddings, every token would simply be an arbitrary integer with no notion of meaning.

---

## How Are Embeddings Generated?

The text processing pipeline is:

```text
Input Text
      ↓
Tokenizer
      ↓
Token IDs
      ↓
Embedding Layer / Embedding Model
      ↓
Embedding Vectors
      ↓
Transformer Layers
```

1. The input text is split into tokens by the tokenizer.
2. Each token is assigned a unique token ID.
3. The embedding layer converts each token ID into a dense embedding vector.
4. These embedding vectors are then processed by the transformer model.

---

## Embeddings Inside an LLM

Within a transformer model:

1. Tokens are converted into embeddings.
2. Positional information (such as RoPE) is added.
3. Query (Q), Key (K), and Value (V) vectors are generated from the embeddings.
4. The attention mechanism computes relationships between tokens.
5. The transformer predicts the next token.

Simplified flow:

```text
Text
  ↓
Tokenizer
  ↓
Token IDs
  ↓
Embedding Layer
  ↓
Embedding Vectors
  ↓
+ Positional Encoding (RoPE)
  ↓
Q, K, V
  ↓
Attention
  ↓
Next Token Prediction
```

---

## Embeddings in RAG

Embeddings are widely used in Retrieval-Augmented Generation (RAG).

Workflow:

1. Documents are converted into embeddings and stored in a vector database.
2. A user's query is converted into an embedding using the same embedding model.
3. Similarity search retrieves the most relevant document embeddings.
4. The retrieved documents are supplied as context to the LLM.

This allows retrieval based on **meaning**, not just exact keyword matching.

---

## Common Use Cases

Embeddings are used in:

- Retrieval-Augmented Generation (RAG)
- Semantic Search
- Vector Databases
- Recommendation Systems
- Document Retrieval
- Question Answering
- Clustering
- Classification

---

## Embeddings vs Token IDs

| Token ID | Embedding |
|----------|-----------|
| Integer identifier | Dense vector representation |
| Represents identity | Represents meaning |
| Produced by tokenizer | Produced by embedding layer/model |
| No semantic information | Encodes semantic relationships |

---
## Final Thought

The next time you hear someone say, "The model understands language," remember:

It doesn't understand words.

It understands vectors.

Embeddings are the bridge that makes that possible.

---
## Common Misconceptions

### Embeddings are not token IDs.

Token IDs uniquely identify tokens.

Embeddings represent the semantic meaning of those tokens.

---


### RoPE does not calculate semantic similarity.

RoPE (Rotary Positional Embeddings) encodes positional information so that the transformer understands word order.

The attention mechanism computes relationships using Query, Key, and Value vectors derived from embeddings.

---

## Key Takeaways

- Embeddings are dense vector representations of tokens.
- Similar meanings produce similar embeddings.
- Neural networks operate on embeddings rather than raw text.
- Attention operates on embeddings after positional information is added.
- Embeddings are fundamental to both LLMs and RAG systems.

---

## References

- Attention Is All You Need (Vaswani et al.)
- RoFormer: Enhanced Transformer with Rotary Position Embedding
- OpenAI Embeddings Documentation
- Sentence Transformers Documentation
