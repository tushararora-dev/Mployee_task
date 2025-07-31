# 📄 Resume Bullet Rewriting with LLaMA 3.1

This project demonstrates how to rewrite weak or generic resume bullet points using various prompting strategies with the `meta-llama/Meta-Llama-3.1-8B-Instruct` model via Hugging Face's `InferenceClient`.

---

## 🔧 Tools & Models Used

- **Model**: `meta-llama/Meta-Llama-3.1-8B-Instruct`
- **Interface**: Hugging Face InferenceClient API
- **Language**: Python
- **Environment**: `.env` file for API key (`HF_TOKEN`)
- **Notebooks**: 10 Jupyter notebooks (each implementing a different prompting strategy)
- **Prompts**: 10 `.txt` files under the `prompt/` directory, each containing a unique prompting template

---

## 🧠 Prompting Strategies

Each notebook demonstrates a distinct prompt engineering technique:

1. **Direct Instruction Prompting** – Clear and concise commands
2. **Role-playing Prompting** – Model behaves as a recruiter or resume expert
3. **Few-shot Prompting** – Learning from given examples
4. **Chain-of-Thought Prompting** – Step-by-step reasoning before rewriting
5. **Keyword-Focused Prompting** – Emphasis on industry-specific terminology
6. **Metrics-Focused Prompting** – Highlights quantifiable outcomes
7. **Simplified Prompting** – Minimal instructions to observe model default behavior
8. **Negative Example Avoidance** – Includes poor examples to avoid
9. **Persona Prompting** – Role-specific guidance (e.g., Data Scientist)
10. **Socratic Prompting** – Uses Q&A-style reflection before rewriting

> **Bonus:** Some notebooks explore **Multi-turn Prompting** for self-refinement.

---

## 🏆 Best Performing Prompt

After empirical comparison across strategies, **Chain-of-Thought Prompting** stood out due to:

- More structured and achievement-focused rewrites  
- Logical reasoning that included measurable impact  
- Minimal vague or generic language  

This approach struck a strong balance between **creativity**, **clarity**, and **effectiveness**.

---

## ⚠️ Challenges Faced

- **Prompt Sensitivity**: Minor changes in text caused major changes in output
- **Rate Limiting**: Introduced `time.sleep()` to avoid API throttling
- **Token Limitations**: Required prompt trimming and formatting control
- **Dynamic Prompting**: Used placeholder `{{bullet}}` to inject resume points into templates across notebooks

---

## 📁 File Structure

```bash
├── prompt/
│   ├── direct_instruction.txt
│   ├── role_playing.txt
│   ├── few_shot.txt
│   ├── chainofthought.txt
│   ├── keyword_focused.txt
│   ├── metrics_focused.txt
│   ├── simplified.txt
│   ├── negative_examples.txt
│   ├── persona_data_science.txt
│   ├── socratic.txt
│
├── direct_instruction.ipynb
├── role_playing.ipynb
├── few_shot.ipynb
├── chainofthought.ipynb
├── keyword_focused.ipynb
├── metrics_focused.ipynb
├── simplified.ipynb
├── negative_examples.ipynb
├── persona_prompt.ipynb
├── socratic_prompt.ipynb
├── bullet.txt
├── .env
