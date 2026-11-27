# Gen-AI Lab Repository (2520030422)

Coursework and practical lab implementations for Generative AI.

---

## 📁 Repository Structure

```text
Gen-AI_2520030422/
├── Week1/
│   ├── main.py              # Basic LLM invocation using Google GenAI SDK
│   ├── requirements.txt     # Python dependencies
│   ├── .env.example         # Template for environment variables
│   └── .gitignore
├── Week2/
│   ├── llm_client.py        # Modular LLM client supporting Gemini and Ollama
│   ├── main.py              # Interactive CLI to test LLM providers
│   ├── test-client.py       # Unit tests with FakeProvider
│   ├── requirements.txt     # Python dependencies
│   └── .env.example         # Template for environment variables
├── Week3/
│   ├── cost_calculator.py   # Token and cost calculation utilities
│   ├── llm_client.py        # Multi-provider client with token tracking
│   ├── mongo_logger.py      # MongoDB integration for audit logging
│   ├── main.py              # Interactive application with cost & DB logging
│   ├── requirements.txt     # Python dependencies
│   └── .env.example         # Template for environment variables
├── Week4/
│   ├── main.py              # Multilingual tokenizer comparison (BPE, WordPiece, SentencePiece)
│   ├── requirements.txt     # Python dependencies
│   ├── tokenizer_results.csv# Exported token count & ratio comparison results
│   ├── Week-4.docx          # Week 4 lab report
│   └── Screenshot *.png     # Execution screenshots
├── Week5/
│   ├── main.py              # Tokenization comparison, API cost & context window calculator
│   ├── week5_token_comparison.csv # Exported multilingual token comparison results
│   ├── WEEK5 code.docx      # Week 5 lab report
│   └── Screenshot *.png     # Execution screenshots
├── Week6/
│   ├── main.py              # Baseline LLM evaluation runner against golden question set
│   ├── golden_set.json      # Golden Q&A evaluation dataset with keywords
│   ├── baseline_results.csv # Exported evaluation scores and responses
│   ├── requirements.txt     # Python dependencies
│   ├── Week6.docx           # Week 6 lab report
│   └── Screenshot *.png     # Execution screenshots
├── Week7/
│   ├── main.py              # Next-token logits & top-k probability inspection with GPT-2
│   ├── requirements.txt     # Python dependencies
│   ├── week7_probability_results.csv # Exported top-k candidate token probabilities
│   └── Week7.docx           # Week 7 lab document
└── Week8/
    ├── main.py              # Scaled Dot-Product & Multi-Head Attention from scratch in PyTorch
    ├── requirements.txt     # Python dependencies
    └── Week8.docx           # Week 8 lab document
```

---

## 🚀 Overview by Week

### Week 1: Introduction to Generative AI SDK
- Direct integration with Google's GenAI Python SDK (`google-genai`).
- Environment variable configuration for secure API key handling.
- Basic prompt completion with `gemini-3.8-flash`.

### Week 2: Provider Abstraction & Testing
- Abstract base class (`LLMProvider`) interface for modularity.
- Implementations for:
  - **GeminiProvider**: Cloud-based Google Gemini models.
  - **OllamaProvider**: Local open-source models via Ollama.
- Unit testing with mock/fake providers (`test-client.py`).

### Week 3: Cost Optimization & MongoDB Logging
- Real-time token usage tracking for input and output.
- Dynamic cost calculation across model tiers.
- MongoDB persistence for query prompts, responses, token counts, and execution metrics.

### Week 4: Tokenizer Comparison Lab
- Compares BPE (`openai-community/gpt2`), WordPiece (`google-bert/bert-base-multilingual-cased`), and SentencePiece Unigram (`google/mt5-small`) across English, Telugu, and Hindi text.
- Computes token counts and token-to-word ratios and exports results to `tokenizer_results.csv`.

### Week 5: Tokenization & Token Economics
- Evaluates multilingual tokenization overhead across English, Telugu, and Hindi (`week5_token_comparison.csv`).
- Models daily and monthly LLM API costs from input/output token rates and usage assumptions.
- Calculates context window utilization across system, conversation, and user input tokens.

### Week 6: Golden Set Baseline Evaluation
- Evaluates a local Ollama model (`llama3.2`) against `golden_set.json` using keyword-coverage scoring.
- Assigns `PASS`/`REVIEW`/`ERROR` status per question and exports baseline `v0.1` metrics to `baseline_results.csv`.

### Week 7: Next-Token Probabilities & Logits Inspection
- Loads `openai-community/gpt2` using Hugging Face `transformers` and PyTorch (`torch`).
- Inspects raw next-token logits, applies softmax to compute probabilities, and extracts top-5 candidate tokens across sample prompts.
- Exports prompt, rank, candidate token, token ID, and probability results to `week7_probability_results.csv`.

### Week 8: Scaled Dot-Product & Multi-Head Attention
- Implements `scaled_dot_product_attention` (with optional causal masking) from scratch using PyTorch.
- Implements a `MultiHeadAttention` `nn.Module` with linear projections (`W_Q`, `W_K`, `W_V`, `W_O`) and head splitting/recombination.
- Verifies tensor shapes and outputs for both single-head and multi-head attention.

---

## ⚙️ Setup and Installation

1. **Clone the repository:**
   ```bash
   git clone https://github.com/CharanTejReddy-bit/Gen-AI_2520030422.git
   cd Gen-AI_2520030422
   ```

2. **Configure Environment Variables:**
   - For each week directory, copy `.env.example` to `.env` and fill in your credentials:
     ```bash
     cp Week1/.env.example Week1/.env
     ```
   - Provide your `GEMINI_API_KEY`.

3. **Install Dependencies:**
   - Navigate into the relevant week folder and run:
     ```bash
     pip install -r requirements.txt
     ```
