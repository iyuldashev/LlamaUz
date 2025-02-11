![image/png](https://cdn-uploads.huggingface.co/production/uploads/665548499ccb17d967f29a74/Dvp01TiCw7xgR8k7EVCDA.png)

**Fine-tuned LLaMA-3.1-8B model for Uzbek language tasks**

This project contains the fine-tuned LLaMA-3.1-8B model for various Uzbek natural language processing (NLP) tasks such as text generation, question answering, and summarization. The model has been trained on a diverse dataset of Uzbek text, including content from Wikipedia, news articles, and books.

---

## 🚀 Features

- **Language**: Uzbek
- **Model Size**: 8 billion parameters
- **Base Model**: Meta LLaMA-3.1
- **Tasks Supported**:
  - Text generation
  - Question answering
  - Summarization
  - General language understanding

---

## 📋 Usage

You can load and use the model directly with the Hugging Face `transformers` library.

### Installation

1. Install the necessary Python libraries:
   ```bash
   pip install transformers bitsandbytes peft
Load the model and tokenizer:
python
Copy code
from transformers import AutoTokenizer, AutoModelForCausalLM

# Load the model and tokenizer
```
model_name = "IzzatilloAi/LlaMa-3.1-8B-Uz"
tokenizer = AutoTokenizer.from_pretrained(model_name)
model = AutoModelForCausalLM.from_pretrained(model_name, device_map="auto", load_in_4bit=True)


# Generate text
prompt = "O'zbekiston tarixi haqida ma'lumot bering."
inputs = tokenizer(prompt, return_tensors="pt")
outputs = model.generate(inputs["input_ids"], max_length=100)
print(tokenizer.decode(outputs[0], skip_special_tokens=True))
```
🏋️‍♂️ Training Details
Dataset
Sources:
Uzbek Wikipedia
Local Uzbek news websites
Uzbek books and literature
Size: Approximately 1GB of cleaned Uzbek text.
Training Configuration
Hardware: 2 x NVIDIA RTX 4090 GPU (24GB memory)
Epochs: 1
Batch Size: 16
Learning Rate: 2e-5
Tools Used
Transformers: Hugging Face library for model training and inference.
BitsAndBytes: For 4-bit quantization.
PEFT: Parameter-efficient fine-tuning.

