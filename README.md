Project
LLM Fine-Tuning for Disease Suggestion Based on Symptoms
Symptoms

🔗 Colab Notebook: https://colab.research.google.com/drive/1kkDK53j0dtEGafCIU_Ak6AbY1pRdqaJu

Objective:

Fine-tune a large language model to predict possible diseases based on symptom inputs. The model provides a short explanation and a medical disclaimer.

Dataset
- Kaggle Dataset: [Disease and Symptoms](https://www.kaggle.com/datasets/choongqianzheng/disease-and-symptoms)
- We used `DiseaseAndSymptoms.csv` to create `train.jsonl` and `test.jsonl`.

Model
- Model used: TinyLLaMA-1.1B-Chat
- Fine-tuning method: LoRA
- Target modules: q_proj, v_proj
- LoRA config: r=8, alpha=32, dropout=0.1
- Training: 2 epochs, batch size 2, gradient accumulation steps 4, learning rate 2e-4

Training Environment
- Google Colab
- GPU:Tesla T4
- Torch dtype: float16

Demo Instructions
1. Load the fine-tuned model from `tinyllama_finetuned/`.
2. Run the function `generate_output(symptoms_text)` with any symptoms input.
3. Example queries:
    - Symptoms: Fever, headache, body pain  
      Output: Disease: Dengue  
      Note: This is not medical advice. Consult a doctor.

Outputs
- Confusion Matrix: `confusion_matrix.png`
- Demo outputs: `demo_output.txt`
- JSONL datasets: `train.jsonl`, `test.jsonl`


