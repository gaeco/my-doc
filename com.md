# Hello

```
import torch
from datasets import load_dataset
from transformers import AutoProcessor, Qwen2_5_VLForConditionalGeneration
from peft import LoraConfig
from trl import SFTTrainer, SFTConfig

model_id = "/models/Qwen2.5-VL-7B-Instruct"  # local path, air-gapped

model = Qwen2_5_VLForConditionalGeneration.from_pretrained(
    model_id, torch_dtype=torch.bfloat16, attn_implementation="flash_attention_2",
)
processor = AutoProcessor.from_pretrained(model_id)

peft_config = LoraConfig(
    r=16, lora_alpha=32, lora_dropout=0.05, bias="none",
    target_modules=["q_proj", "k_proj", "v_proj", "o_proj",
                    "gate_proj", "up_proj", "down_proj"],
    # vision tower usually frozen for defect detection; add merger/visual modules only if needed
)

train_ds = load_dataset("json", data_files="/data/pallet_defects.jsonl")["train"]

args = SFTConfig(
    output_dir="/runs/qwen25vl-defect-lora",
    per_device_train_batch_size=1,
    gradient_accumulation_steps=8,
    gradient_checkpointing=True,
    bf16=True,
    learning_rate=2e-4,
    num_train_epochs=3,
    logging_steps=10,
    save_strategy="epoch",
    dataset_kwargs={"skip_prepare_dataset": True},  # let the VLM collator handle multimodal samples
)

trainer = SFTTrainer(
    model=model,
    args=args,
    train_dataset=train_ds,
    peft_config=peft_config,
    processing_class=processor,   # passing the processor triggers VLM mode
)
trainer.train()



```
