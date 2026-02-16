Call Center Conversation Generation

End-to-end solution for generating realistic 3–6 turn call center conversations from short service summaries.

This project was developed as part of a Machine Learning Researcher evaluation task.



🎯 Task Objective

Given a short summary describing a customer service request, generate a realistic and structurally correct conversation between:

Client
Agent
Constraints:
3–6 turns
Strict role alternation
High semantic consistency with the summary
Natural conversational tone
No hallucinated details

🧠 Approach
1️⃣ Baseline Experiments

I initially experimented with:
Google FLAN-T5 models (base, large)
Instruction tuning only
Synthetic data augmentation
External datasets from the internet
Observed Issues:
Generic responses
Weak alignment with summaries
Structural inconsistencies
Quality degradation from synthetic data
Domain mismatch from external datasets
These approaches did not achieve sufficient performance across semantic consistency and structural compliance metrics.

2️⃣ Final Model Variant (Selected Solution)

The final solution uses:

Prompt-structured supervised fine-tuning

Strict format conditioning

Domain-aligned training data only

Controlled max token length

Explicit role alternation supervision

Training Format
Generate a realistic call center conversation.

Summary:
{summary_text}

Conversation:


This significantly improved:

Information accuracy

Summary-to-dialogue alignment

Structural reliability

Conversational realism

📊 Evaluation Criteria

The solution was optimized for:

Information Accuracy (50%)

Semantic Consistency (20%)

Structural Compliance (20%)

Fluency & Realism (10%)

Manual validation confirmed strong performance across all categories.

📁 Project Structure
├── conversation_generation_task.ipynb
├── generated_test.json
├── report.pdf
├── requirements.txt
└── README.md

🚀 How to Run
pip install -r requirements.txt


Open the notebook:

conversation_generation_task.ipynb


Run training and generation cells sequentially.

🔍 Key Design Decisions

Avoided synthetic data to prevent distribution shift

Enforced strict structural supervision

Limited generation length to prevent hallucinations

Prioritized semantic faithfulness over verbosity

⚠️ Limitations

Domain-specific to structured service summaries

May produce generic responses for vague inputs

No RLHF or reward-based optimization applied

🏁 Conclusion

Multiple variants were evaluated, including FLAN models with synthetic and external data augmentation. These approaches did not meet required quality thresholds.

The final prompt-structured supervised fine-tuning approach achieved strong semantic consistency, structural compliance, and realistic conversational flow.

This solution balances robustness, simplicity, and reproducibility for real-world call center dialogue generation tasks.
