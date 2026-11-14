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
└── Week3/
    ├── cost_calculator.py   # Token and cost calculation utilities
    ├── llm_client.py        # Multi-provider client with token tracking
    ├── mongo_logger.py      # MongoDB integration for audit logging
    ├── main.py              # Interactive application with cost & DB logging
    ├── requirements.txt     # Python dependencies
    └── .env.example         # Template for environment variables
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
