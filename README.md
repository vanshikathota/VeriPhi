
# Veriphi - Benchmarking LLM for Automated Verilog RTL Code Generation

[![Python](https://img.shields.io/badge/Python-3.10-blue.svg)](https://www.python.org/)
[![HuggingFace](https://img.shields.io/badge/Model-HuggingFace-orange)](https://huggingface.co/)

## 📌 Project Overview

**Veriphi** explores the use of Large Language Models (LLMs) for automating the generation of Verilog RTL (Register Transfer Level) code — a vital process in semiconductor and digital circuit design. This project fine-tunes Microsoft’s **Phi-2** model to automatically produce Verilog code from high-level natural language prompts.

By automating this process, we aim to:
- Reduce development time.
- Minimize human errors.
- Make chip design accessible to non-experts.
- Boost productivity in the semiconductor industry.

## 🚀 Features

- ✅ Fine-tuning of the **Phi-2 LLM (2.7B parameters)** on a custom Verilog dataset.
- ✅ Uses **Parameter Efficient Fine-Tuning (PEFT)** techniques: LoRA & 4-bit Quantization.
- ✅ Batch-wise fine-tuning to overcome limited VRAM on Google Colab/Kaggle.
- ✅ Verilog code generation from **natural language prompts**.
- ✅ Performance evaluation via functional and syntactic correctness testing.
- ✅ Model hosted on Hugging Face Hub, integrated with **Ollama API**.

## 📂 Repository Structure

```
.
├── finetunning.ipynb     # Notebook for fine-tuning the Phi-2 model
├── testing.ipynb         # Notebook for testing the fine-tuned model
├── requirements.txt      # Required Python dependencies
├── README.md             # This file
```

## 🧑‍💻 Technologies Used

| Component        | Technology                                    |
|-----------------|----------------------------------------------|
| **Model**       | Phi-2 (2.7B parameters) via Hugging Face      |
| **Training**    | PEFT (LoRA, 4-bit Quantization) using SFTTrainer |
| **Frameworks**  | Transformers, PEFT, BitsandBytes, Accelerate  |
| **Cloud Platforms** | Google Colab (T4 GPU), Kaggle (T4 GPU)    |
| **Deployment**  | Hugging Face Hub, Ollama API                 |
| **Frontend**    | React.js (Prompt Window UI)                  |
| **Backend**     | Node.js, Express.js                          |
| **Database**    | MongoDB with Mongoose                        |

## ⚙️ Setup & Installation

1. **Clone this repository**:
   ```bash
   git clone https://github.com/vanshikathota/Veriphi.git
   cd Veriphi
   ```

2. **Create & activate a virtual environment** (Optional but recommended):
   ```bash
   python -m venv venv
   source venv/bin/activate   # On Windows: venv\Scripts\activate
   ```

3. **Install dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

4. **Run Notebooks**:
   - Open `finetunning.ipynb` in Google Colab or Jupyter for fine-tuning.
   - Open `testing.ipynb` for testing generated Verilog RTL code.

## 📌 Methodology Summary

- Dataset: 108,971 Verilog code rows.
- Split into batches of 1,000 rows due to **15GB VRAM limits** on Colab/Kaggle.
- Fine-tuned incrementally with SFTTrainer and PEFT (LoRA + 4-bit quantization).
- Models pushed to Hugging Face Hub after each batch for version control.
- Evaluation includes syntactic and functional testing using test benches.

## 🎯 Results

- High-quality Verilog code generation from natural prompts.
- Verified via simulation tools and functional correctness tests.
- Significant reduction in manual RTL coding effort and design time.

## 🔮 Future Scope

- Extend code generation to other HDL languages like **VHDL**.
- Improve batch-wise fine-tuning with advanced hyperparameter optimization.
- Explore **multi-language support** and **automated design validation** frameworks.



## 📞 Contact

For any queries or discussions, reach out via [GitHub Issues](https://github.com/vanshikathota/Veriphi/issues).
