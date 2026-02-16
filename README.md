#Call Center Conversation Generation

End-to-end solution for generating realistic 3–6 turn call center conversations from short service summaries.

This project was developed as part of a Machine Learning Researcher evaluation task.

---

 🎯 Task Objective

Given a short summary describing a customer service request, generate a realistic and structurally correct conversation between:

- **Client**
- **Agent**

 Constraints:
- 3–6 turns
- Strict role alternation
- High semantic consistency with the summary
- Natural conversational tone
- No hallucinated details




# 1️⃣ Baseline Experiments

I initially experimented with:

- Google FLAN-T5 models (`base`, `large`)
- Instruction tuning only
- Synthetic data augmentation
- External datasets from the internet

# Observed Issues:
- Generic responses
- Weak alignment with summaries
- Structural inconsistencies
- Quality degradation from synthetic data
- Domain mismatch from external datasets

These approaches did not achieve sufficient performance across semantic consistency and structural compliance metrics.


# 2️⃣ Final Model Variant (Selected Solution)

The final solution uses:

- Prompt-structured supervised fine-tuning
- Strict format conditioning
- Domain-aligned training data only
- Controlled max token length
- Explicit role alternation supervision

#### Training Format


