# 🎯 Custom GPT Coding-Only Assistant

**Domain-specific GPT-2** that speaks only one language: **Python**.
It refuses to entertain general chit-chat, giving you clean, readable Python code whenever you ask the right questions.

---

## 🚀 Features

* **Python-Only Responses:** Never drifts off-topic; only answers Python coding queries.
* **Keyword-Based Filtering:** Detects Python-related prompts using intelligent keyword matching.
* **GPT-2 Powered:** Uses Hugging Face GPT-2 for generating Python code.
* **Pretty & Readable:** Formats GPT-2 outputs as clean, indented Python code blocks.
* **Witty Rejection:** For non-coding prompts, it politely says:

  > ❌ I can only answer Python coding questions.

---

## 🛠️ Setup

Install required libraries:

```bash
pip install transformers torch
```

Import libraries and load the GPT-2 model:

```python
import torch
from transformers import AutoTokenizer, AutoModelForCausalLM

model_name = "gpt2"
tokenizer = AutoTokenizer.from_pretrained(model_name)
model = AutoModelForCausalLM.from_pretrained(model_name)

device = torch.device("cuda" if torch.cuda.is_available() else "cpu")
model.to(device)
```

---

## 💡 How It Works

1. **Prompt Filtering:**
   The input is checked for Python-related keywords (like `function`, `import`, `class`, `pandas`, etc.).

2. **Code Generation:**
   If the prompt is Python-related, GPT-2 generates code.
   Non-coding prompts get a witty rejection message.

3. **Formatting:**
   The output is cleaned and wrapped as an indented Python code block for readability.

---

## ⚡ Usage Example

```python
prompts = [
    "Write a Python function to calculate factorial.",
    "Explain inheritance in Python classes.",
    "What is the capital of France?"
]

for prompt in prompts:
    print(f"\nPrompt: {prompt}")
    print(generate_response(prompt))
```

**Sample Output:**

````
Prompt: Write a Python function to calculate factorial.
```python
    def factorial(n):
        if n == 0:
            return 1
        return n * factorial(n-1)
````

```
Prompt: What is the capital of France?
❌ I can only answer Python coding questions.
```

---

## 📈 Why This Project Rocks

* Keeps GPT-2 **focused** on one domain.
* **Prevents hallucinations** for non-coding questions.
* Lightweight and easy to run locally or on Colab.
* Fully **extensible**: You can upgrade filtering with ML classifiers or fine-tune GPT-2 on Python datasets.

---

## 🔮 Next-Level Ideas

* Use **GPT-2 Medium/Large** for more coherent Python outputs.
* Replace GPT-2 with **code-specialized models** like `CodeGPT` or `Codex`.
* Add **whitelist-based post-processing** to prevent fake imports and non-existent functions.

---

## 📝 License

MIT License – code freely, responsibly, and Pythonically. 🐍
