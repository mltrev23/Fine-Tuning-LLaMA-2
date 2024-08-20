# Fine-tuning Llama-2

This project aims to fine-tune the Llama-2 language model using Hugging Face's Transformers library. By following these steps, you can fine-tune the model and use it for inference.

---
## Prerequisites

Before getting started, make sure you have the following:

- Hugging Face API token (HF token)
- Python installed on your system
  
---
## Setup

1. Clone this repository to your local machine.

    ```bash
    git clone https://github.com/mltrev23/Fine-Tuning-LLaMA-2/
    ```

2. Install the required packages using the following command:

   ```bash
   pip install -r requirements.txt
   ```


---


## Fine-tuning Llama-2

To fine-tune Llama-2, run the following command:

```shell
python main.py
```

This command will fine-tune the model using the specified dataset and save the fine-tuned model to the `llama-2-7b-chat-guanaco` folder.

### Custom Data Ingestion

To ingest your own data for fine-tuning, you'll need to modify the code in your script. Here's an example of how to load a custom dataset:
    
```python
from datasets import load_dataset

# Load your dataset from a text file
dataset = load_dataset('text', data_files='datasets/bittensor.txt', split='train')
```

Make sure to replace `'datasets/bittensor.txt'` with the path to your dataset file.

Happy fine-tuning!

---

## Inference

To perform inference using the fine-tuned Llama-2 model, follow these steps:

1. Ensure you've successfully fine-tuned Llama-2 as explained in the Fine-tuning Llama-2 section.

2. After training, you can run inference directly in the `main.py` script. The fine-tuned model will be used for generating text based on prompts.

### Example Inference

You can modify the prompt in the `main.py` file to test the model:
    
```python
prompt = "What is bittensor?"
result = pipe(f"<s>[INST] {prompt} [/INST]")
print(result[0]['generated_text'])
```

This will output the generated text based on the prompt provided.

---

### Additional Notes

- Ensure you have all necessary dependencies installed as listed in `requirements.txt`.
- Adjust the training parameters in the `TrainingArguments` section of `main.py` as needed to fit your requirements.


### Summary of Changes

- The command to run the fine-tuning process is simplified to just `python main.py`.
- The data ingestion section is updated to reflect how to load a dataset using the `datasets` library.
- Inference instructions are included to show how to modify prompts for testing the model.
- Additional notes encourage users to check dependencies and adjust training parameters. 
