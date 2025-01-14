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

## 📦 Repository Contents

- `README.md`: This file, explaining the project.
- Model files and configurations:
  - `config.json`
  - `pytorch_model.bin` (or `model.safetensors`)
  - `tokenizer.json`
  - `tokenizer_config.json`
- Training arguments and logs (if applicable).

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
model_name = "IzzatilloAi/LlaMa-3.1-8B-Uz"
tokenizer = AutoTokenizer.from_pretrained(model_name)
model = AutoModelForCausalLM.from_pretrained(model_name, device_map="auto", load_in_4bit=True)

# Generate text
prompt = "O'zbekiston tarixi haqida ma'lumot bering."
inputs = tokenizer(prompt, return_tensors="pt")
outputs = model.generate(inputs["input_ids"], max_length=100)
print(tokenizer.decode(outputs[0], skip_special_tokens=True))
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
Precision: Mixed (FP16/4-bit)
Tools Used
Transformers: Hugging Face library for model training and inference.
BitsAndBytes: For 4-bit quantization.
PEFT: Parameter-efficient fine-tuning.

📜 License
This project is licensed under the MIT License. See the LICENSE file for more information.

🙏 Acknowledgments
Meta AI: For providing the LLaMA base model.
Hugging Face: For the transformers library and ecosystem.
Uzbek AI Community: For contributing datasets and resources.
🤝 Contributions
Contributions are welcome! Feel free to open issues or submit pull requests to improve the model or this repository.

🛠️ Future Work
Further fine-tuning for domain-specific Uzbek tasks.
Incorporating additional datasets for broader coverage.
Exploring deployment options for production environments.
