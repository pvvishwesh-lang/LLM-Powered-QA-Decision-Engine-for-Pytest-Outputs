An end to end QA Decision Engine that analyzes PyTest output and provides QA decisions using rule based logic and fine tuned LLM (LoRA). 


This converts noisy pytest outputs into actionable outputs like 'ALLOW', 'WARN' and 'PASS',enabling intelligent testing and analysis, even in CI/CD pipelines.



LoRA config:

lora_config = LoraConfig(
    r=8,
    lora_alpha=16,
    target_modules=["q_proj", "v_proj"],
    lora_dropout=0.05,
    task_type="CAUSAL_LM"
)


Sample Prompt:

Instruction:
You are a QA decision engine. Analyze pytest output and return a JSON decision.

Input:
ModuleNotFoundError: No module named 'bitsandbytes'

Output:

Sample Output:

{'classification': 'ModuleNotFound',
 'qa_label': 'packaging_issue',
 'qa_decision': 'BLOCK'}
 
